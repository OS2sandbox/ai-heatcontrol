---
title: "System Architecture"
layout: diagram
---


## Overview

This document describes the system architecture for the OS2 AI Heat Control platform using FIWARE as the central data infrastructure.

## Architecture Diagram

```mermaid
flowchart LR
 subgraph FIWARE ["FIWARE Stack"]
        IOT[IoT Agent]
        ORION[Orion-LD]
        QL[Quantum Leap]
    end

    subgraph INPUT ["Input Sources"]
        MQTT[MQTT]
        HTTP[HTTP POST]
        LORA[LoRaWAN]
        CTS[CTS-anlæg]
        WEATHER[Vejrdata API]
    end
    
    subgraph pipelines
    P1[Ingest]
    P2[Rules]
    end

    subgraph PLATFORM["Infrastructure platform"]
        
    PIPELINE[Pipeline Orchestrator]
    NATS[Message Queue]
    end
   
    
    subgraph VIZ ["Visualization"]
        GRAFANA[Grafana]
    end

    ORION --> PIPELINE 
    PIPELINE -.- P1 & P2
    MQTT & HTTP & LORA & WEATHER --> PIPELINE
    CTS <-->|GET / POST|PIPELINE 

    PIPELINE --> NATS --> IOT
    IOT --> ORION
    ORION --> QL
    ORION <-..-|GET /entities| GRAFANA
```

## Hvorfor denne løsning?

Traditionelt skal man bygge sin egen integrationsplatform med databaser, device management, API'er og brugergrænseflader. Det tager tid og kræver vedligeholdelse.

**Her gør vi det anderledes:**

- **Ingen database** - data flyder bare igennem
- **Ingen brugergrænseflade** - alt er konfigurationsfiler
- **Kun input → transform → output** - præcis det der er brug for
- **Alt er deklarativt YAML** - pipelines som kode i stedet for at skrive custom programmering
- **NATS håndterer buffering og levering** - så systemet er stabilt selv under stor belastning

**Resultatet er simpelt:** Du skriver configs der fortæller "hvad" der skal ske - ikke hvordan. Og så virker det.

