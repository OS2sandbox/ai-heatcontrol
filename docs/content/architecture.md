---
title: "System Architecture"
layout: diagram
---

# Reference arkitektur
_Referencearkitekturen beskriver en open source-platform, der opfylder aiheatcontrols behov. Den er visualiseret som en [C4-model](https://c4model.com/) på to niveauer: **systemkontekst** (platformen set udefra) og **containere** (platformens interne komponenter)._

{{< card type="note" icon="doc" title="Målgruppe" >}}
Dette referencearkitektur dokument henvender sig til tekniske beslutningstagere, arkitekter og leverandører.
Diagrammerne anvender engelske fagtermer, da det antages at disse er de genkendelige
standardbetegnelser på tværs af it-arkitekter og leverandører.
{{< /card >}}




## System landskab
_Et samlet højniveau overblik over platformen, der illustrerer modtagelse af data fra indendørssensorer, CTS-anlæg og vejrdata — og hvordan platformen interagerer med anvendere, udviklere og driftsfolk. For en detaljeret opdeling af de interne komponenter, se **Container Diagram (Level 2)** nedenfor._

```mermaid
%%{init: {"theme": "base", "themeVariables": {"primaryColor": "#C8D5CE", "primaryTextColor": "#3F4A44", "primaryBorderColor": "#AAB1C2", "lineColor": "#9DB59D", "secondaryColor": "#D7C1E3", "tertiaryColor": "#F2F4F3", "edgeLabelBackground": "#E8EAE9", "edgeLabelText": "#3F4A44"}, "flowchart": {"htmlLabels": false, "subGraphTitleMargin": {"top": 25, "bottom": 30}, "nodeSpacing": 40, "rankSpacing": 55}}}%%
flowchart LR
    SENSORS("Indoor Temperature Sensors")
    CTS("CTS Building System")
    WEATHER("Weather Data")
    PLATFORM(["AI Heat Control <br> Platform"])
    OPERATOR("👤 Building Operator")
    ENGINEER("👤 Building Engineer")
    SCIENTIST("👤 Data Scientist")
    TEAM("👤 Platform Team")
    REPO@{ shape: docs, label: "Configuration <br> Repository" }

    SENSORS -->|readings| PLATFORM
    CTS <-->|control| PLATFORM
    WEATHER -->|forecast| PLATFORM
    PLATFORM -.->|dashboards| OPERATOR
    ENGINEER --->|commits building model & prediction| REPO
    SCIENTIST --->|commits prediction model| REPO
    TEAM -->|maintains CI/CD & repository| REPO
    TEAM -.->|operates hosting| PLATFORM
    REPO -.->|CI/CD deploys config| PLATFORM

    style PLATFORM fill:#E4EBE4,stroke:#8DA68D,stroke-width:3px,color:#2D3D2D
    click PLATFORM "#container-diagram" "Click to expand → see internal containers"
```

## Løsnings arkitektur {#container-diagram}
_Løsningsarkitekturen forudsætter to protokol-gateways i organisationens infrastruktur. Der findes open source-implementationer af begge_


```mermaid
%%{init: {"theme": "base", "themeVariables": {"primaryColor": "#C8D5CE", "primaryTextColor": "#3F4A44", "primaryBorderColor": "#AAB1C2", "lineColor": "#8B9BB0", "secondaryColor": "#D7C1E3", "tertiaryColor": "#F2F4F3", "edgeLabelBackground": "#E8EAE9", "edgeLabelText": "#3F4A44"}, "flowchart": {"htmlLabels": false, "subGraphTitleMargin": {"top": 12, "bottom": 14}, "nodeSpacing": 40, "rankSpacing": 40}}}%%
flowchart TB
    classDef oss fill:#e8f5e9,stroke:#2e7d32,color:#1b5e20
    classDef custom fill:#fff3e0,stroke:#e65100,color:#bf360c

    subgraph CFG["Configuration Repository"]
        style CFG fill:#F5F7F6,stroke:#D5D9E0,stroke-width:1px,color:#3F4A44
        CFG_CONFIGS@{ shape: docs, label: "Platform Pipelines Building Models Prediction Configs <br> ML Models" }
    end

    subgraph INPUT["External Systems"]
        style INPUT fill:#F5F7F6,stroke:#D5D9E0,stroke-width:1px,color:#3F4A44
        LORA("Indoor Temperature Sensors")
        GATEWAY["Sensor Gateway"]
        CTS["CTS Building System"]
        CTS_GATEWAY["CTS Gateway"]
        WEATHER["Weather Data"]
        style LORA fill:#F5F2ED,color:#3F4A44
        style CTS fill:#F5F2ED,color:#3F4A44
        style WEATHER fill:#F5F2ED,color:#3F4A44
    end

    subgraph PLATFORM_BOUNDARY["AI Heat Control Platform"]
        style PLATFORM_BOUNDARY fill:#F2F4F3
        GW{{"API Gateway"}}

        subgraph ORCH["Orchestration"]
            style ORCH fill:#F5F7F6,stroke:#D5D9E0,stroke-width:1px,color:#3F4A44
            PIPELINE{{Pipeline Orchestrator}}
        end

        subgraph FWARE["IoT Context Platform"]
            style FWARE fill:#F5F7F6,stroke:#D5D9E0,stroke-width:1px,color:#3F4A44
            IOT{{IoT Agent}}
            BROKER[("Context Broker<br/>+ Historical Storage")]
        end

        subgraph SEMANTIC["Semantic Model"]
            style SEMANTIC fill:#F5F7F6,stroke:#D5D9E0,stroke-width:1px,color:#3F4A44
            SPARQL[("Knowledge Graph")]
        end

        subgraph PREDICT["Prediction Engine"]
            style PREDICT fill:#F5F7F6,stroke:#D5D9E0,stroke-width:1px,color:#3F4A44
            PREDICT_API{{"Predict API"}}
            PREDICT_RUNTIME{{"Prediction Runtime"}}
        end

        NATS(["Message Queue"])

        GRAFANA@{shape: curv-trap, label: "Data Visualization"}
    end

    LORA -->|LoRaWAN| GATEWAY
    GATEWAY --->|HTTP| GW
    CTS -->|BACnet| CTS_GATEWAY
    CTS_GATEWAY -->|MQTT| PIPELINE
    WEATHER --->|HTTP| GW
    GW --> PIPELINE
    CFG_CONFIGS -->|pipeline YAML| PIPELINE
    CFG_CONFIGS -->|loads .ttl| SPARQL
    CFG_CONFIGS -->|.yaml + .rq| PREDICT_API
    CFG_CONFIGS -->|loads .onnx| PREDICT_RUNTIME
    PREDICT_RUNTIME -->|prediction| PREDICT_API
    PIPELINE -->|predict| PREDICT_API
    PREDICT_API -->|semantic| SPARQL
    PREDICT_API -->|context| BROKER
    PREDICT_API -->|setpoints| NATS
    PIPELINE <--->|events| NATS
    NATS ---> IOT
    IOT --> BROKER
    BROKER -->|state| PIPELINE
    BROKER <-..-|queries| GRAFANA

    class GW,PIPELINE,IOT,BROKER,NATS,GRAFANA,SPARQL,GATEWAY,CTS_GATEWAY oss
    class PREDICT_API,PREDICT_RUNTIME custom
    class CFG_CONFIGS custom
```

{{< legend oss="Open Source-komponent" custom="Egenudviklet kode / konfiguration" >}}

## Genbrug af komponenter
_I stedet for at investere i at bygge og vedligeholde sin egen integrationsplatform med databaser, enhedsstyring, API'er og brugergrænseflader – og dermed genopfinde funktionalitet, der allerede findes – er denne referencearkitektur løst koblet og baseret på genbrug af eksisterende Open Source løsninger._

{{< grid columns=3 >}}
{{< card icon="cog" title="API Gateway" >}}
[Envoy Proxy](https://www.envoyproxy.io/docs) - HTTP endpoints for alle datakilder
{{< /card >}}

{{< card icon="cable" title="Pipeline Orchestrator" >}}
[WarpStream Bento](https://warpstreamlabs.github.io/bento/) – deklarative pipelines i et klart og menneskelæsbart format, der transformerer og videresender data
{{< /card >}}

{{< card icon="shield" title="Message Queue" >}}
[NATS JetStream](https://docs.nats.io/nats-concepts/jetstream) – løskobling af datakilder og datamodtagere for at sikre pålidelige dataleverancer under høj belastning
{{< /card >}}

{{< card icon="wrench" title="IoT Agent" >}}
[FIWARE IoT Agent](https://iotagent-node-lib.readthedocs.io/en/latest/) – bro mellem IoT-enheders protokoller og FIWARE Context Broker
{{< /card >}}

{{< card icon="chart" title="Data Visualization" >}}
[Grafana](https://www.grafana.com/docs/) - dashboards og visualisering af entiteter og tidsseriedata
{{< /card >}}

{{< card icon="database" title="FIWARE Stack" >}}
[FIWARE Orion-LD](https://fiware-academy.readthedocs.io/en/latest/core/orion-ld.html) og [TimescaleDB](https://docs.timescale.com/) – underliggende, iot-datamodel, der samler realtidsdata og historik og kan kobles sammen med domænespecifikke bygnings-datamodeller.
{{< /card >}}

{{< card icon="database" title="Knowledge Graph" >}}
[Apache Jena](https://jena.apache.org/), [OpenLink Virtuoso](https://virtuoso.openlinksw.com/) eller [GraphDB](https://www.ontotext.com/products/graphdb/) – SPARQL-triplestore med domænemodellen (Brick+REC). Adskiller bygningslogik fra kildekode via `.ttl`-filer og `.rq`-forespørgsler.
{{< /card >}}

{{< card icon="doc" title="LoRaWAN Gateway" >}}
[ChirpStack Gateway OS](https://github.com/chirpstack/chirpstack-gateway-os) — OpenWrt-baseret embedded OS til LoRa-gateways. Kører på Raspberry Pi + LoRa-concentrator. Videresender sensor-data til platformen via HTTP.
{{< /card >}}

{{< card icon="building" title="CTS Gateway" >}}
[bacnet-mqtt-gateway](https://github.com/novatechflow/bacnet-mqtt-gateway) — Container-baseret BACnet/IP→MQTT bridge med discovery, polling og bidirectional writes. Oversætter CTS-data til MQTT.
{{< /card >}}

{{< /grid >}}

## Konfigurationsstyret workflow
_Platformens forretningslogik styres gennem et versionsstyret git-baseret Configuration Repository, hvor bygningsingeniører, data scientists og platformsteamet vedligeholder konfigurationsfiler frem for kildekode_

{{< grid columns=2 >}}
{{< card title="Bygningsmodel (.ttl)" icon="file" >}}
RDF/Turtle-filer, der beskriver bygningens fysiske komponenter i Brick+REC-ontologien. Indeholder rum, sensorer, varmesløjfer og CTS-punkter.
{{< /card >}}

{{< card title="Prediktionskonfiguration (.yaml + .rq)" icon="cog" >}}
Deklarativ YAML, der definerer hvornår og hvordan en prediktion køres. SPARQL-forespørgsler (.rq) udtrækker de nødvendige data fra vidensgrafens semantiske model.
{{< /card >}}

{{< card title="ML-model (.onnx)" icon="brain" >}}
Trænede ONNX-modeller fra data scientists, der erstatter simpel formel-logik med avancerede prædiktionsmodeller — indlæst direkte af Prediktions-API'et ved opstart.
{{< /card >}}

{{< card title="Pipeline-konfiguration" icon="cable" >}}
Bento-pipeline YAML, der ruter data korrekt mellem input-kilder, prediktions-API og CTS-anlæg — uden at indeholde prediktionslogik.
{{< /card >}}
{{< /grid >}}

Bygningsingeniører og data scientists committer konfiguration til Git. CI/CD validerer og udruller automatisk til platformen, så ændringer træder i kraft uden manuelle driftindgreb. Platformteamet vedligeholder CI/CD-pipelines og hosting-infrastrukturen.
