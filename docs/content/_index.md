---
title: Home
---

## Kerneproduktet

OS2 AI Heat Control er en fælles digital infrastruktur, der indsamler og strukturerer data fra CTS-anlæg og IoT-sensorer og anvender dem til prædiktiv varmestyring i kommunale bygninger.

En referencealgoritme beregner prædiktive setpunkter for fremløbstemperatur på varmesløjfer (radiator- og gulvvarmeanlæg) — inden for definerede tidsplaner og med robust fallback. Connectors udstiller et åbent API, så data kan sendes til og modtages fra bygningsautomatikken.

Datamodellen bygger på de åbne ontologier **BrickSchema** og **RealEstateCore** — en fælles semantik, der gør løsningen genbrugelig, sammenlignelig og leverandøruafhængig.

## De fire grundelementer

{{< cards >}}
{{< card title="Datafundamentet" icon="database" >}}
En fælles datamodel for de minimumsdata, der er nødvendige for intelligent varmestyring.

Data fra CTS-anlæg på anvendersiden er en forudsætning for, at produktet kan fungere. Historiske data, rumtemperatur og vejrdata udgør fundamentet for at kunne arbejde ensartet, sammenligneligt og skalerbart på tværs af kommuner og bygninger.
{{< /card >}}

{{< card title="Reguleringsmotoren" icon="cog" >}}
En fælles referencealgoritme, som sender prædiktive setpunkter til bygningsautomatik.

Reguleringsmotoren anvender målt rumtemperatur, vejrdata, historik og tidsplaner til at beregne optimale setpunkter for fremløbstemperatur og varmekurver. En robust fallback-strategi er en central del af styringslogikken.
{{< /card >}}

{{< card title="Connector-laget" icon="cable" >}}
Standardiserede integrationer til CTS- og IoT-systemer.

Connector-laget gør det muligt at koble lokale bygningsinstallationer ind i en fælles ramme og reducerer afhængigheden af proprietære løsninger.
{{< /card >}}

{{< card title="Implementerbarhed og drift" icon="shield" >}}
Kommunal driftsegnethed, cybersikkerhed og lave implementeringsomkostninger.

Kerneproduktet skal ikke kun være teknisk velfunderet — det skal også kunne implementeres enkelt, driftes økonomisk og godkendes i kommunal praksis.
{{< /card >}}
{{< /cards >}}

## Kommerciel værdi for markedet

Kerneproduktet er åbent og skalerbart. Markedet forventes at bygge kommercielle services oven på den fælles platform.

{{< cards >}}
{{< card title="Connectors & integration" icon="wrench" >}}
Leverandører af CTS- og IoT-systemer forventes selv at udvikle og vedligeholde connectors efter de åbne connector-specifikationer og det standardiserede API.
{{< /card >}}

{{< card title="Installation, drift & support" icon="headset" >}}
Flere leverandører kan tilbyde lokal installation, løbende drift og support som service oven på det åbne kerneprodukt — en multi-leverandør-model.
{{< /card >}}

{{< card title="Avancerede modeller" icon="brain" >}}
Udvikl specialiserede AI/ML-algoritmer, der bygger videre på referencealgoritmen for prædiktive setpunkter med mere avanceret optimering.
{{< /card >}}

{{< card title="Analyse & dashboards" icon="chart" >}}
Skab rapportering, benchmarking og visualisering på tværs af bygninger baseret på den fælles datamodel og åbne ontologier.
{{< /card >}}
{{< /cards >}}

## Governance & ansvar

OS2 AI Heat Control styres gennem en fælles governancemodel, hvor ansvar og beslutningskompetence er tydeligt fordelt mellem fire aktører.

{{< cards >}}
{{< card title="OS2-fællesskabet" icon="users" >}}
- Ejer kerneproduktet (datamodel, referencealgoritme, connector-specifikationer)
- Sætter retning via governance-board
{{< /card >}}

{{< card title="Kommunerne" icon="building" >}}
- Implementerer og drifter løsningen i egne bygninger
- Bidrager til udvikling med krav, testdata og feedback
{{< /card >}}

{{< card title="Leverandører (CTS/IoT & software)" icon="wrench" >}}
- Udvikler connectors til den åbne platform efter OS2's specifikationer
- Tilbyder kommercielle services
{{< /card >}}

{{< card title="Driftsorganisationen" icon="users" >}}
- Drifter fælles infrastruktur med hosting ved OS2
- Sikrer dataportabilitet
{{< /card >}}
{{< /cards >}}

## Datamodellen

Baseret på [Brick Schema](https://brickschema.org) og [RealEstateCore](https://www.realestatecore.io) — åbne ontologier for bygningsdata.

OS2-specifikke styringsklasser udvider standarden for kommunal varmestyring. Ved at basere datamodellen på etablerede, åbne ontologier undgår løsningen proprietære dataformater og sikrer, at bygningsdata kan deles, beriges og genbruges på tværs af systemer og leverandører — en fælles 'ordbog' for bygningsdata.

<img src="/datamodel-diagram.svg" alt="Relationsdiagram over datamodellen med RealEstateCore, Brick Schema og OS2 klasser">

[Brick + REC integration](https://docs.brickschema.org/extra/brick-rec.html)