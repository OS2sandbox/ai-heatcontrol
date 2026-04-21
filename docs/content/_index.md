---
title: Home
---

# OS2 AI Heat Control

Prædiktive setpunkter til kommunale varmeanlæg — bygget på en fælles datamodel med åbne ontologier og en referencealgoritme, som markedet kan bygge videre på.

## Kerneproduktet

OS2 AI Heat Control er en fælles digital infrastruktur, der indsamler og strukturerer data fra CTS-anlæg og IoT-sensorer og anvender dem til prædiktiv varmestyring i kommunale bygninger.

En referencealgoritme beregner prædiktive setpunkter for fremløbstemperatur på varmesløjfer (radiator- og gulvvarmeanlæg) — inden for definerede tidsplaner og med robust fallback. Connectors udstiller et åbent API, så data kan sendes til og modtages fra bygningsautomatikken.

Datamodellen bygger på de åbne ontologier **BrickSchema** og **RealEstateCore** — en fælles semantik, der gør løsningen genbrugelig, sammenlignelig og leverandøruafhængig.

## De fire grundelementer

### Datafundamentet

En fælles datamodel for de minimumsdata, der er nødvendige for intelligent varmestyring.

Data fra CTS-anlæg på anvendersiden er en forudsætning for, at produktet kan fungere. Historiske data, rumtemperatur og vejrdata udgør fundamentet for at kunne arbejde ensartet, sammenligneligt og skalerbart på tværs af kommuner og bygninger.

### Reguleringsmotoren

En fælles referencealgoritme, som sender prædiktive setpunkter til bygningsautomatik for fremløbstemperatur af varmesløjfer (radiator- og gulvvarmeanlæg).

Reguleringsmotoren anvender målt rumtemperatur, vejrdata, historik og tidsplaner til at beregne optimale setpunkter for fremløbstemperatur og varmekurver.

En robust fallback-strategi er en central del af styringslogikken, så bygningerne altid har en sikker driftstilstand.

### Connector-laget

Standardiserede integrationer til CTS- og IoT-systemer samt eksterne datakilder.

Connector-laget gør det muligt at koble lokale bygningsinstallationer ind i en fælles ramme og reducerer afhængigheden af proprietære løsninger.

Connector-specifikationerne fungerer som en åben kontrakt: de definerer præcist, hvilke data der skal leveres, i hvilket format og med hvilken frekvens.

### Implementerbarhed og drift

Kommunal driftsegnethed, cybersikkerhed og lave implementeringsomkostninger.

Kerneproduktet skal ikke kun være teknisk velfunderet — det skal også kunne implementeres enkelt, driftes økonomisk og godkendes i kommunal praksis.

Der skal tages stilling til NIS2-compliance, herunder en generel vurdering af, hvad der udgør kritisk infrastruktur i løsningen.

## Kommerciel værdi for markedet

Kerneproduktet er åbent og skalerbart. Markedet forventes at bygge kommercielle services oven på den fælles platform.

### Connectors & integration

Leverandører af CTS- og IoT-systemer forventes selv at udvikle og vedligeholde connectors efter de åbne connector-specifikationer og det standardiserede API.

### Installation, drift & support

Flere leverandører kan tilbyde lokal installation, løbende drift og support som service oven på det åbne kerneprodukt — en multi-leverandør-model.

### Avancerede modeller

Udvikl specialiserede AI/ML-algoritmer, der bygger videre på referencealgoritmen for prædiktive setpunkter med mere avanceret optimering.

### Analyse & dashboards

Skab rapportering, benchmarking og visualisering på tværs af bygninger baseret på den fælles datamodel og åbne ontologier.

## Governance & ansvar

OS2 AI Heat Control styres gennem en fælles governancemodel, hvor ansvar og beslutningskompetence er tydeligt fordelt mellem fire aktører.

### OS2-fællesskabet

- Ejer kerneproduktet (datamodel, referencealgoritme, connector-specifikationer)
- Sætter retning via governance-board

### Kommunerne

- Implementerer og drifter løsningen i egne bygninger
- Bidrager til udvikling med krav, testdata og feedback

### Leverandører (CTS/IoT & software)

- Udvikler connectors til den åbne platform efter OS2's specifikationer
- Tilbyder kommercielle services

### Driftsorganisationen

- Drifter fælles infrastruktur med hosting ved OS2
- Sikrer dataportabilitet

## Datamodellen

Baseret på Brick Schema og RealEstateCore — åbne ontologier for bygningsdata.

OS2-specifikke styringsklasser udvider standarden for kommunal varmestyring. Ved at basere datamodellen på etablerede, åbne ontologier undgår løsningen proprietære dataformater.

### Relationer

| Fra | Til | Relation |
|-----|-----|----------|
| Room | Building | locatedIn |
| Temperature_Sensor | Room | isPointOf |
| Weather_Station | Building | monitors |
| Schedule | Building | servesBuilding |
| Setpoint | Building | servesBuilding |