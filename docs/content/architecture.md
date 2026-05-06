---
title: "System Architecture"
layout: diagram
---


## Overblik

Dette dokument beskriver systemarkitekturen for OS2 AI Heat Control platformen. Systemet bruger en Pipeline Orchestrator til at koordinere dataflows fra forskellige inputkilder gennem deklarative pipelines, med FIWARE (Orion-LD, IoT Agent, Quantum Leap) som central datainfrastruktur.

## Architecture Diagram

```mermaid
flowchart LR
subgraph FIWARE ["FIWARE Stack"]
        IOT@{ shape: subroutine, label: "IoT Agent" }
        ORION@{ shape: h-cyl, label: "Context Broker" }
        QL@{ shape: fr-rect, label: "Timeseries API" }
        TS[(Timeseries<br/>Storage)]
    end

    subgraph INPUT ["Input Sources"]
        LORA((LoRaWAN<br/>Indoor temp))
        GATEWAY[[LoRaWAN<br/>Gateway]]
        CTS[[CTS-anlæg<br/>REST API]]
        WEATHER[[Vejrdata API<br/>REST API]]
    end
    
    subgraph VCS ["Versioned Configs"]
    P1@{ shape: doc, label: "Ingest" }
    P2@{ shape: doc, label: "Rules" }
    end

    subgraph PLATFORM["Infrastructure platform"]
    NATS@{ shape: subroutine, label: "Message Queue" }
    INGRESS@{ shape: hex, label: "API Gateway" }
    PIPELINE@{ shape: h-cyl, label: "Pipeline Orchestrator" }
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
{{< card icon="database" title="Input Kilder" >}}
LoRaWAN sensorer (indoor temp), CTS-anlæg, Vejrdata API
{{< /card >}}

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

{{< card icon="doc" title="Versioned Configs" >}}
Ingest og Rules pipelines - deklarative konfigurationer versioneret i Git
{{< /card >}}

{{< card icon="headset" title="Context Brooker" >}}
[FIWARE Orion-LD](https://fiware-academy.readthedocs.io/en/latest/core/orion-ld.html) - context broker med entitet historik
{{< /card >}}

{{< card icon="database" title="Timeseries Storage" >}}
[TimescaleDB](https://docs.timescale.com/) - PostgreSQL tidsserie-database udviddelse tilgængelig via Quantum Leap API
{{< /card >}}
{{< /grid >}}

**Resultatet er simpelt:** Du skriver configs der fortæller "hvad" der skal ske - ikke hvordan. Og så virker det.

