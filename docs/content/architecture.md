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

```mermaid
%%{init: {"theme": "base", "themeVariables": {"primaryColor": "#C8D5CE", "primaryTextColor": "#3F4A44", "primaryBorderColor": "#AAB1C2", "lineColor": "#8B9BB0", "secondaryColor": "#D7C1E3", "tertiaryColor": "#F2F4F3", "edgeLabelBackground": "#E8EAE9", "edgeLabelText": "#3F4A44"}, "flowchart": {"htmlLabels": false, "subGraphTitleMargin": {"top": 12, "bottom": 14}, "nodeSpacing": 40, "rankSpacing": 40}}}%%
flowchart TB
    classDef oss fill:#e8f5e9,stroke:#2e7d32,color:#1b5e20
    classDef custom fill:#fff3e0,stroke:#e65100,color:#bf360c
    subgraph INPUT["Input Sources"]
        style INPUT fill:#F5F7F6,stroke:#D5D9E0,stroke-width:1px,color:#3F4A44
        LORA("Indoor Temperature Sensors")
        GATEWAY["Sensor Gateway"]
        CTS["CTS Building System"]
        WEATHER["Weather Data"]
        style LORA fill:#F5F2ED,color:#3F4A44
        style GATEWAY fill:#F5F2ED,color:#3F4A44
        style CTS fill:#F5F2ED,color:#3F4A44
        style WEATHER fill:#F5F2ED,color:#3F4A44
    end

    GW{{"API Gateway"}}

    subgraph ORCH["Orchestration"]
        style ORCH fill:#F5F7F6,stroke:#D5D9E0,stroke-width:1px,color:#3F4A44
        PIPELINE{{Pipeline Orchestrator}}
        CONFIG@{shape: doc, label: "Configuration"}
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
    end

    NATS(["Message Queue"])

    GRAFANA@{shape: curv-trap, label: "Data Visualization"}

    LORA ---> GATEWAY
    GATEWAY --->|HTTP| GW
    CTS --->|HTTP| GW
    WEATHER --->|HTTP| GW
    GW --> PIPELINE
    PIPELINE -..- CONFIG
    PIPELINE -->|predict| PREDICT_API
    PREDICT_API -->|semantic| SPARQL
    PREDICT_API -->|context| BROKER
    PREDICT_API -->|setpoints| NATS
    PIPELINE <--->|events| NATS
    NATS ---> IOT
    IOT --> BROKER
    BROKER -->|state| PIPELINE
    BROKER <-..-|queries| GRAFANA

    class GW,PIPELINE,IOT,BROKER,NATS,GRAFANA oss
    class CONFIG,SPARQL,PREDICT_API custom
```

{{< legend >}}

## Genbrug af komponenter
_I stedet for at investere i at bygge og vedligeholde sin egen integrationsplatform med databaser, enhedsstyring, API'er og brugergrænseflader – og dermed genopfinde funktionalitet, der allerede findes – er denne referencearkitektur løst koblet og baseret på genbrug af eksisterende Open Source løsninger._

{{< grid columns=2 >}}
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
{{< /grid >}}
