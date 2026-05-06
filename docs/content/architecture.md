---
title: "System Architecture"
layout: diagram
---


## Overblik

Dette dokument beskriver systemarkitekturen for OS2 AI Heat Control platformen. Systemet bruger en Pipeline Orchestrator til at koordinere dataflows fra forskellige inputkilder gennem deklarative pipelines, med FIWARE (Orion-LD, IoT Agent, Quantum Leap) som central datainfrastruktur.

## Architecture Diagram

```mermaid
%%{init: {"theme": "base", "themeVariables": {"primaryColor": "#C8D5CE", "primaryTextColor": "#3F4A44", "primaryBorderColor": "#AAB1C2", "lineColor": "#8B9BB0", "secondaryColor": "#D7C1E3", "tertiaryColor": "#F2F4F3", "edgeLabelBackground": "#E8EAE9", "edgeLabelText": "#3F4A44"}}}%%
flowchart LR
    subgraph FIWARE ["FIWARE Stack"]
        style FIWARE fill:#F2F4F3,stroke:#F2F4F3,stroke-width:2px,color:#64748B
        IOT{{IoT Agent}}
        ORION("Context Broker")
        QL(["Timeseries API"])
        TS[(Timeseries<br/>Storage)]
    end

    subgraph INPUT ["Input Sources"]
        style INPUT fill:#F2F4F3,stroke:#F2F4F3,stroke-width:2px,color:#64748B
        LORA((LoRaWAN<br/>Indoor temp))
        GATEWAY[[LoRaWAN<br/>Gateway]]
        CTS[[CTS-anlæg<br/>REST API]]
        WEATHER[[Vejrdata API<br/>REST API]]
        style LORA fill:#F5F2ED,color:#3F4A44
        style GATEWAY fill:#F5F2ED,color:#3F4A44
        style CTS fill:#F5F2ED,color:#3F4A44
        style WEATHER fill:#F5F2ED,color:#3F4A44
    end
    
    subgraph VCS ["Versioned Configs"]
        style VCS fill:#F2F4F3,stroke:#F2F4F3,stroke-width:2px,color:#64748B
        P1@{ shape: doc, label: "Ingest" }
        P2@{ shape: doc, label: "Rules" }
        style P1 fill:#F5F2ED,color:#3F4A44
        style P2 fill:#F5F2ED,color:#3F4A44
    end

    subgraph PLATFORM ["Infrastructure platform"]
        style PLATFORM fill:#F2F4F3,stroke:#F2F4F3,stroke-width:2px,color:#64748B
        NATS(["Message Queue"])
        INGRESS{API Gateway}
        PIPELINE{{Pipeline Orchestrator}}
        GRAFANA@{ shape: curv-trap, label: "Grafana" }
    end
    
    
    ORION --> PIPELINE 
    PIPELINE -..- P1 & P2
    WEATHER --->|HTTP| INGRESS
    LORA --> GATEWAY --->|HTTP| INGRESS
    INGRESS --> PIPELINE
    CTS <--->|GET / POST| INGRESS 

    PIPELINE <---> NATS ---------> IOT
    IOT --> ORION
    ORION --> QL
    QL --> TS
    ORION <-..-|GET /entities| GRAFANA
    TS <-.-|queries| GRAFANA
```

## Hvorfor denne løsning?

Istedet for at investere i at bygge og vedligeholde sin egen integrationsplatform med databaser, device management, API'er og brugergrænseflader er denne reference arkitektur løstkoblet og består af genbrug af eksisterende løsninger.

### Genbrug af Open Source

{{< grid columns=3 >}}
{{< card icon="cog" title="API Gateway" >}}
[Envoy Proxy](https://www.envoyproxy.io/docs) - HTTP endpoints for alle datakilder
{{< /card >}}

{{< card icon="cable" title="Pipeline Orchestrator" >}}
[WarpStream Bento](https://warpstreamlabs.github.io/bento/) - deklarative pipelines der transformerer og router data
{{< /card >}}

{{< card icon="shield" title="Message Queue" >}}
[NATS JetStream](https://docs.nats.io/nats-concepts/jetstream) - buffering og reliable delivery under høj belastning
{{< /card >}}

{{< card icon="wrench" title="IoT Agent" >}}
[FIWARE IoT Agent](https://iotagent-node-lib.readthedocs.io/en/latest/) - device management og protokol konvertering
{{< /card >}}

{{< card icon="chart" title="Data Visualization" >}}
[Grafana](https://www.grafana.com/docs/) - dashboards og visualisering af entiteter og tidsseriedata
{{< /card >}}

{{< card icon="database" title="FIWARE Stack" >}}
[FIWARE Orion-LD](https://fiware-academy.readthedocs.io/en/latest/core/orion-ld.html) - context broker + [TimescaleDB](https://docs.timescale.com/) for timeseries via Quantum Leap API
{{< /card >}}
{{< /grid >}}

**Resultatet er simpelt:** Du skriver configs der fortæller "hvad" der skal ske - ikke hvordan. Og så virker det.

