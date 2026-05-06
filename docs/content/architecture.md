---
title: "System Architecture"
layout: diagram
---


## Overblik

Dette dokument beskriver systemarkitekturen for OS2 AI Heat Control platformen. Systemet bruger en Pipeline Orchestrator til at koordinere dataflows fra forskellige inputkilder gennem deklarative pipelines, med FIWARE (Orion-LD, IoT Agent, Quantum Leap) som central datainfrastruktur.

### Dataflow

{{< cards >}}
{{< card icon="database" title="Input Kilder" >}}
LoRaWAN sensorer (indoor temp), CTS-anlæg, Vejrdata API
{{< /card >}}

{{< card icon="cog" title="API Gateway" >}}
Envoy Proxy - HTTP endpoints for alle datakilder
{{< /card >}}

{{< card icon="cable" title="Pipeline Orchestrator" >}}
WarpStream Bento - deklarative pipelines der transformerer og router data
{{< /card >}}

{{< card icon="shield" title="Message Queue" >}}
NATS JetStream - buffering og reliable delivery under høj belastning
{{< /card >}}

{{< card icon="wrench" title="IoT Agent" >}}
FIWARE IoT Agent - device management og protokol konvertering
{{< /card >}}

{{< card icon="headset" title="Context Brooker" >}}
FIWARE Orion-LD - context broker med entitet historik
{{< /card >}}

{{< card icon="database" title="Time Series DB" >}}
TimescaleDB - tidsserie-database via Quantum Leap API
{{< /card >}}
{{< /cards >}}

## Architecture Diagram

```mermaid
flowchart LR
subgraph FIWARE ["FIWARE Stack"]
        IOT[IoT Agent]
        ORION[Orion-LD]
        QL[Database API]
        TS[(Timeseries<br/>DB)]
    end

    subgraph INPUT ["Input Sources"]
        LORA((LoRaWAN<br/>Indoor temp))
        GATEWAY[[LoRaWAN<br/>Gateway]]
        CTS[[CTS-anlæg<br/>REST API]]
        WEATHER[[Vejrdata API<br/>REST API]]
    end
    
    subgraph pipelines
    P1[Ingest]
    P2[Rules]
    end

    subgraph PLATFORM["Infrastructure platform"]
    INGRESS[API Gateway]
    PIPELINE[Pipeline Orchestrator]
    NATS[Message Queue]
    end
    
    
    subgraph VIZ ["Visualization"]
        GRAFANA[Grafana]
    end

    ORION --> PIPELINE 
    PIPELINE -..- P1 & P2
    WEATHER -->|HTTP| INGRESS
    LORA --> GATEWAY -->|HTTP| INGRESS
    INGRESS --> PIPELINE
    CTS <-->|GET / POST| INGRESS 

    PIPELINE --> NATS --> IOT
    IOT --> ORION
    ORION --> QL
    QL --> TS
    ORION <-..-|GET /entities| GRAFANA
    TS <-..-|queries| GRAFANA
```

## Hvorfor denne løsning?

Traditionelt skal man bygge sin egen integrationsplatform med databaser, device management, API'er og brugergrænseflader. Det tager tid og kræver vedligeholdelse.

**Her gør vi det anderledes:**

- **Ingen custom database** - alt lagres i FIWARE (Orion-LD + Quantum Leap/TimescaleDB)
- **Ingen brugergrænseflade** - alt er konfigurationsfiler
- **Pipeline Orchestrator** styrer dataflows automatisk
- **Deklarative YAML pipelines** - kun "hvad" der skal ske, ikke hvordan
- **NATS håndterer buffering og levering** - stabilitet under høj belastning

**Resultatet er simpelt:** Du skriver configs der fortæller "hvad" der skal ske - ikke hvordan. Og så virker det.

