📆 _sidst opdateret: {{ site.time | date: '%B %d, %Y' }}_

# Referat : OS2 AI Heat Control projektmøde 21.04.2026

**Status**
- [x] Mødet kalendersat
- [x] Dagsorden udarbejdet
- [x] Referat påbegyndt
- [x] Referat sendt til godkendelse
- [ ] Referat godkendt
- [ ] Referat publiceret  

## Mødefakta
  
**Mødenavn**: OS2 AI Heat Control projektmøde nr. 5  
**Tid**: 21.04.2026 kl. 9-12  
**Sted**: Nytorv 11, Kolding Kommune

#### Deltagere

- [x] Mikkel Groot Andersen, Silkeborg Kommune, IT
- [x] Martin Hansen / Michael Kjær Maagaard, Kolding Kommune
- [x] Jakob Hovgaard Kaiser, Aarhus Kommune
- [x] Anders Aschlund Bach Burkahl, Ikast-Brande Kommune
- [x] Villads Laraignou Mønsted, Gladsaxe Kommune
- [x] Anna-Lis Berg, OS2-sekretariatet
- [x] Jakob Thøtt Nørby, 4BC

#### Afbud

- [x] Jesper Buchhardt, Silkeborg Kommune, EJD
- [x] Rasmus Frey, OS2-sekretariatet

#### Faciliteret af

- [x] Jakob Thøtt Nørby, 4BC (mødeleder og referet)

#### Observatører / gæster

- [x] Pernille Bech Darbroudi, Kolding Kommune

---

## Mødeindhold

### Mødebeskrivelse

Formålet med mødet var at følge op på seneste projektmøde, gennemgå den aktuelle handlingslog og orientere projektgruppen om læring fra møder med OS2, FleetOptimizer og Silkeborg Kommune.

Mødet havde desuden fokus på fastlæggelse af de videre rammer for kerneproduktet, herunder brug af RealEstateCore og BrickSchema som grundlag for ontologi/datamodel, samt anvendelse af relevante elementer fra OS2sandbox/gps-connector.

Endelig blev deltagerne introduceret til GitHub som fælles arbejdsrum for referater, handlingslog, beslutningslog, dokumentation og open source softwareudvikling.

### Mødepræsentation og baggrundsmateriale

- Mødepræsentation: **05 Præsentation - OS2 AI Heat Control 21-04-2026**
- Seneste referat: **[04 Referat - OS2 AI Heat Control 24-03-2026 v1](https://github.com/OS2sandbox/ai-heatcontrol/blob/main/projektadministration/m%C3%B8der/pm4.md)**
- Baggrund fra tidligere workshop om kerneprodukt: **[03 Referat - OS2 AI Heat Control 10-03-2026](https://github.com/OS2sandbox/ai-heatcontrol/blob/main/projektadministration/m%C3%B8der/pm3.md)**
- Datamodelskitse: vedlagt skitse med RealEstateCore, BrickSchema og OS2-udvidelser:
  <img width="1478" height="791" alt="image" src="https://github.com/user-attachments/assets/dbf5435b-a2a0-4aa8-9ee7-2c65dda1c4b1" />

- GitHub repository: **[OS2sandbox/ai-heatcontrol](https://github.com/OS2sandbox/ai-heatcontrol)**
- Referenceprojekt: **[OS2sandbox/gps-connector](https://github.com/OS2sandbox/gps-connector)**

### Dagsorden

1. Formalia  
   1. Verifikation af deltagere, mødeleder og referent  
   2. Bemærkninger til seneste referat  
2. General housekeeping  
   1. Gennemgang af handlingslog  
   2. Opfølgning på igangværende aktiviteter  
3. Tema 1: Orientering fra møder med OS2, FleetOptimizer og Silkeborg Kommune  
4. Tema 2: Fastlæggelse af grundelementer i kerneprodukt  
5. Tema 3: Introduktion til GitHub og rammerne for open source softwareudvikling  
6. Eventuelt og kig til næste møde  

#### Beslutnings- og action logs

- Link til beslutningslog: https://github.com/OS2sandbox/ai-heatcontrol/tree/main/projektadministration/beslutninger
- Link til risikolog: https://github.com/OS2sandbox/ai-heatcontrol/tree/main/projektadministration/risici
- Link til handlingslog / Issues: https://github.com/OS2sandbox/ai-heatcontrol/issues

---

## Mødereferat

### AD 1: Formalia

- [x] Deltagere og afbud verificeret
- [x] Ingen bemærkninger til seneste referat

Der var ingen bemærkninger til seneste referat.

Det blev samtidig bemærket, at referater og bemærkninger fremadrettet håndteres via GitHub. GitHub skal anvendes som fælles arbejdsrum for projektets dokumentation, historik, opgaver og ændringsspor.

---

### AD 2: General housekeeping

#### Status på igangværende aktiviteter / handlingslog

Fremadrettet flyttes handlingsloggen til **Issues på GitHub**. Afsluttede punkter slettes eller arkiveres løbende, så handlingsloggen holdes aktiv og overskuelig.

| Nr. | Kilde | Handling | Ansvarlig | Deadline | Status/kommentar |
|---:|---|---|---|---|---|
| 6 | PM1 | Afklare fælles indkøb af LoRaWAN-sensorer | Deltagerkommuner | Afventer | Udkast under udarbejdelse. Punkt videreføres. |
| 7 | PM1 | Udarbejde kommunikationsstrategi | OS2 / AB | Inden næste møde | OS2 har skabelon for kommunikationsindsats, der fremsendes til JN. |
| 8 | PM2 | Sikring af korrekt faktureringsprocedure via OS2 | Gladsaxe Kommune / RP | Snarest | Gladsaxe Kommune fremsender EAN-nummer til RP. |
| 11 | PM2 | Undersøge mulighed for samarbejde med BIPED-projekt | JK | I proces | JK har haft dialog med projektet. Det skal fortsat vurderes, om samarbejde vil bringe værdi til OS2 AI Heat Control. |
| 12 | PM4 | Etablering af faggrupper | JN | Forud for udbud | Faggrupper skal nedsættes til at teste løsningen i praksis. Faggrupper bør bestå af personer tæt på drift og slutanvendelse. |
| 13 | PM4_4.1 | Plan for dialog med SKI-leverandører | JN / OS2 | Snarest | Markedsdialog skal bl.a. omfatte potentielle SKI-leverandører. |
| 14 | PM4_5.2 | Afklare muligheder i SKI-aftaler | JK | Snarest | JK undersøger relevante SKI-aftaler, herunder om der findes dynamiske indkøbsaftaler. |
| 15 | PM4_5.3 | Udarbejde bilag om non-funktionelle krav | AB / OS2 | Snarest | Bilag om non-funktionelle krav udarbejdes og kobles til projektets kravspecifikation. |
| 16 | PM5 | Kvalitetstjek af datamodel | JN / JK / SDU | Snarest | SDU foreslås inddraget til kvalitetstjek af datamodelskitse. JK foreslog oplæg fra SDU-ansat. |
| 17 | PM5 | Anvende relevante elementer fra OS2sandbox/gps-connector | Projektgruppen / JN | I det videre arbejde | Det blev besluttet at anvende relevante elementer fra GPS-connector-projektet som inspiration/byggeklodser. |
| 18 | PM5 | Dokumentere beslutning om grundelementer og ontologi | JN / projektgruppen | Snarest | Der udarbejdes beslutning om grundelementer i kerneproduktet samt anvendelse af RealEstateCore og BrickSchema som ontologisk grundlag. |

#### Opfølgning på budget og ressourcer

- [ ] **Budget:** Ikke særskilt behandlet på mødet.
- [ ] **Ressourcer:** Ikke særskilt behandlet på mødet.
- [ ] Roller i GitHub-baseret udvikling skal afklares nærmere, herunder særligt Maintainer-rollen.

---

### AD 3: Tema 1 - Orientering fra møder med OS2, FleetOptimizer og Silkeborg Kommune

Der blev orienteret om erfaringer fra dialog med OS2 og FleetOptimizer. FleetOptimizer anvender en komponentbaseret arkitektur, som er udviklet efter dialog med Jan K. fra OS2. Projektet har aktuelt flere integrationer til flådestyringssystemer, og der blev peget på, at flere open source “byggeklodser” kan være relevante som inspiration for OS2 AI Heat Control.

Særligt blev **[OS2sandbox/gps-connector](https://github.com/OS2sandbox/gps-connector)** nævnt som et relevant referenceprojekt. Projektet beskrives som en FIWARE-baseret stack med fokus på GPS- og IoT-dataproducenter. Det blev besluttet, at OS2 AI Heat Control skal anvende relevante elementer fra GPS-connector-projektet i det videre arbejde med arkitektur, integrationer og datainfrastruktur.

Der blev også orienteret om dialog med Silkeborg Kommune / Francine. Herfra blev det fremhævet, at **RealEstateCore** og **BrickSchema** vurderes som den rigtige retning for datamodellering. Samtidig blev det pointeret, at løsningen skal have fleksibilitet i forhold til “Source of Truth”, så projektet ikke låser sig for tidligt til én bestemt datakilde, struktur eller driftsmodel.

Der blev desuden drøftet mulighed for at få **SDU** til at kvalitetstjekke projektets datamodel. JK foreslog, at en SDU-ansat inviteres til at holde et indlæg eller på anden måde bidrage med faglig kvalitetssikring af datamodelskitsen.

Den vedlagte datamodelskitse viser et muligt samspil mellem:

- **RealEstateCore:** fx `rec:Room` og `rec:Building`
- **BrickSchema:** fx `brick:HVAC_Zone`, `brick:Temperature_Sensor`, `brick:Weather_Station` og tidsseriereference
- **OS2-udvidelser:** fx `os2:Setpoint`, `os2:FallbackStrategy` og `os2:Schedule`

Skitsemæssigt kobles rum, bygning, HVAC-zone, temperaturmålinger, tidsserier, vejrdata, setpunkter, fallback-strategier og driftsplaner sammen i én samlet model. Datamodellen skal kvalitetstjekkes og videreudvikles, før den kan indgå som endeligt grundlag for kravspecifikation og udviklingsdialog.

---

### AD 4: Tema 2 - Fastlæggelse af grundelementer i kerneprodukt

Projektgruppen drøftede grundelementerne i kerneproduktet med afsæt i det tidligere arbejde fra PM3 og PM4. På PM3 blev der arbejdet med SKAL-, VIGTIGT- og EKSTRA-krav til løsningen, herunder at produktet skal kunne godkendes af kommunale IT-afdelinger i forhold til cybersikkerhed. På PM4 blev kerneproduktet beskrevet med fire hovedspor: datafundament, reguleringsmotor, connector-lag samt implementerbarhed og drift.

Det blev aftalt, at der skal udarbejdes en egentlig **beslutning** om grundelementerne i kerneproduktet, herunder at **RealEstateCore** og **BrickSchema** anvendes som ontologisk og datamodelmæssigt udgangspunkt.

Kerneproduktet struktureres fortsat omkring fire hovedspor:

1. **Datafundamentet**  
   En fælles datamodel for de minimumsdata, der er nødvendige for intelligent varmestyring. Datamodellen skal være enkel, modulær og baseret på åbne standarder/ontologier, herunder RealEstateCore og BrickSchema.

2. **Reguleringsmotoren**  
   En fælles referencealgoritme eller baseline-styringslogik, der kan sende prædiktive setpunkter til styring af fremløbstemperatur i varmeanlæg. Der skal samtidig være fokus på fallback-strategier.

3. **Connector-laget**  
   Standardiserede integrationer til CTS, IoT-systemer og eksterne datakilder. Connector-laget skal definere, hvilke data der skal leveres, i hvilket format og med hvilken frekvens, så leverandører kan koble sig på løsningen på en ensartet måde.

4. **Implementerbarhed og drift**  
   Løsningen skal kunne godkendes, implementeres og driftes i kommunal praksis. Det omfatter blandt andet cybersikkerhed, NIS2-relevante vurderinger, driftsegnethed, lave implementeringsomkostninger og mulighed for leverandørskifte.

Det blev understreget, at grundelementerne skal verificeres yderligere sammen med en kommende udviklingspartner og i det efterfølgende test- og udviklingsforløb.

#### Beslutning

Der udarbejdes en beslutning i projektets beslutningslog om:

1. Grundelementerne i kerneproduktet, herunder anvendelse af RealEstateCore og BrickSchema som ontologisk udgangspunkt

---

### AD 5: Tema 3 - Introduktion til GitHub og rammerne for open source softwareudvikling

Mødedeltagerne blev introduceret til open source softwareudvikling og GitHub som fælles arbejdsform.

Open source blev introduceret med følgende hovedpointer:

- Koden er åben og kan ses af andre.
- Andre kan bruge, ændre og dele koden.
- Udviklingen sker i fællesskab.
- OS2 anvender typisk **MPL 2.0** som open source-licens for kode.
- OS2 anvender typisk **CC BY-SA** til dokumentation og andet materiale, der ikke er kode.

Der blev desuden gennemgået en typisk open source arbejdsgang:

1. Et behov, en fejl eller et forbedringsønske beskrives som en **Issue**.
2. Ønsket vurderes og prioriteres af fællesskabet.
3. Ændringen igangsættes i et særskilt arbejdsspor, en **Branch**.
4. Udvikleren foreslår ændringen via en **Pull Request**.
5. Ændringen gennemgås i **Review**.
6. Godkendte ændringer indarbejdes i fælles løsning via **Merge**.
7. Hele forløbet dokumenteres.

GitHub blev forklaret som et fælles arbejdsrum for software og dokumentation, på samme måde som man i andre fagsystemer samler dokumentation, opgaver, historik og samarbejde ét sted.

Følgende begreber blev gennemgået:

- **Repository:** samlet projektområde
- **Issue:** sag, ticket, opgave eller forbedringsønske
- **Branch:** arbejdsspor eller testspor
- **Commit:** gemt og dokumenteret ændring
- **Pull Request:** ændringsforslag
- **Review:** faglig gennemgang/kvalitetssikring
- **Merge:** godkendt indarbejdelse i fælles løsning

Mødedeltagerne fik oprettet bruger til GitHub, så projektet fremadrettet kan anvende GitHub til referater, Issues, handlingslog, beslutningslog og dokumentation.

Roller i projektet blev også berørt:

- **Project Coordinator:** koordinerer opgaver, flow og fremdrift.
- **Maintainer:** har ansvar for den fælles løsning, godkender ændringer og indarbejder dem i fælles løsning. Rollen er aktuelt vakant og skal afklares.

Der aftales et særskilt møde med OS2 om beslutningslog, struktur for GitHub og håndtering af projektets dokumentation.

---

### AD 6: Eventuelt og kig til næste møde

#### Næste skridt

- GitHub sættes op som fælles arbejdsrum for OS2 AI Heat Control.
- Referater, handlingslog og projektets centrale dokumentation flyttes til GitHub.
- Handlingslog flyttes til **Issues**.
- Næste møde, som var planlagt som fysisk møde i Ikast-Brande den **05.05.2026**, ændres til et kort Teams-møde.
- Der er forslag om fysisk møde i Ikast-Brande den **03.06.2026**.
- Mødet i Silkeborg den **02.06.2026** foreslås aflyst.
- Projektet præsenteres for **GreenInsight / Gate21** den **19.05.2026**.

#### Eventuelt

- [x] Ingen yderligere punkter noteret.

---
