📆 _sidst opdateret: {{ site.time | date: '%B %d, %Y' }}_

# Referat : OS2 AI Heat Control Projektmøde nr. 4 24. marts 2026

**Status**
- [x] Mødet kalendersat
- [x] Dagsorden udarbejdet
- [x] Referat påbegyndt
- [x] Referat sendt til godkendelse
- [x] Referat godkendt
- [x] Referat publiceret


## Mødefakta

**Mødenavn**: OS2 AI Heat Control Projektmøde nr. 4  
**Tid**: 24. marts 2026  
**Sted**: Online  

**Projekt**: OS2 AI Heat Control  
**Emne**: Projektmøde nr. 4  
**PM**: PM4  
**Mødedato**: 24. marts 2026  
**Referatdato**: 27. marts 2026  
**Rev. dato**: 7. april 2026 (markeret med rødt)


#### Deltagere:

| Navn | Organisation | Init. |
|---|---|---|
| Jesper Buchhardt | Silkeborg Kommune, EJD | JB |
| Mikkel Groot Andersen | Silkeborg Kommune, IT | MA |
| Michael Kjær Maagaard | Kolding Kommune | MKM |
| Jakob Hovgaard Kaiser | Aarhus Kommune | JK |
| Anders Aschlund Bach Burkahl | Ikast-Brande Kommune | ABB |
| Anna-Lis Berg | OS2-sekretariatet | AB |
| Jakob Thøtt Nørby (referent) | 4BC | JN |


#### Afbud:

| Navn | Organisation | Init. |
|---|---|---|
| Martin Hansen | Kolding Kommune | MH |
| Rasmus Frey | OS2-sekretariatet | RF |


#### Faciliteret af:

- Jakob Thøtt Nørby (referent)


#### Mailes til

Mødedeltagere inkl deltagere, der har meldt afbud


## Møde Indhold

### Møde beskrivelse

Projektmøde nr. 4


### Møde præsentation og baggrundsmateriale

- Vedlagt referat: -


### Dagsorden

1. Bemærkninger til seneste referat
2. Gennemgang af handlingslog
3. Præsentation af oplæg til definition af kerneprodukt
4. Plan for dialog med markedet
5. Næste skridt
6. Eventuelt


#### Beslutnings og action logs

Handlingslog gennemgået under AD 2.


## Møde referat

### AD 1: Bemærkninger til seneste referat

#### 1.1.

Ingen bemærkninger.


### AD 2: Gennemgang af handlingslog

#### 2.1.

| Nr. | Kilde | Handling | Ansvarlig | Deadline | Status/kommentar |
|---|---|---|---|---|---|
| 2 | PM1 | Fastlægge endelig projektorganisering og governance – herunder etablering af styregruppe og projektgruppe samt afklaring og fastlæggelse af formelle rammer for samarbejdet (økonomi, indbetaling m.v.) | OS2 / RF | Ultimo marts | Punkt lukkes.<br><br>Projektorganisering er på plads. Senere tages der stilling til en eventuel opsplitning i styregruppe og koordinationsgruppe. |
| 6 | PM1 | Afklare fælles indkøb af LoRaWAN-sensorer | Deltager-kommuner | Afventer | Udkast under udarbejdelse. |
| 7 | PM1 | Udarbejde kommunikationsstrategi | OS2 / AB | Inden næste møde | OS2 har skabelon for kommunikationsindsats, der fremsendes til JN |
| 8 | PM2 | Sikring af korrekt faktureringsprocedure via OS2 | JK | Inden påske | Afklaring og implementering er igangsat ved RF. OS2 savner EAN-nummer fra Aarhus Kommune. JK fremsender EAN-nummer til RF. |
| 9 | PM2 | Fremsendelse af materiale vedr. organiseringsmodel (fx OS2 Valghalla) | OS2 / RF |  | Punkt lukkes. |
| 11 | PM2 | Undersøge mulighed for samarbejde med BIPED-projekt | JK | I proces | JK har haft dialog med projekt. Det skal undersøges nærmere om det vil bringe værdi til OS2AIHC at indgå i et samarbejde. |
| 12 | PM4 | Etablering af faggrupper | JN | Forud for udbud | Faggrupper til at teste løsning i praksis skal nedsættes, når<br><br>Faggruppe består af personer tæt på driften/slutanvendere |


### AD 3: Præsentation af oplæg til definition af kerneprodukt

#### 3.1.

JN præsenterede oplæg til definition af kerneprodukt, hvor der er fokus på fire grundelementer (kommentarer fra mødet til højre i kursiv):


#### 1) Datafundamentet

En fælles datamodel for de minimumsdata, der er nødvendige for intelligent varmestyring.

Historiske data, rumtemperatur og vejrdata udgør fundamentet for at kunne arbejde ensartet, sammenligneligt og skalerbart på tværs af kommuner og bygninger.

Datamodellen standardiserer formater, begreber og semantik på tværs af bygninger og kommuner, så data ikke blot indsamles, men kan forstås og sammenlignes ensartet.

*[kommentarer på mødet]:*

Data fra CTS-anlæg (på anvender-siden) er en forudsætning for, at produkt kan fungere. Det behandles derfor heller ikke særskilt i dette projekt, at data kan stilles til rådighed under givne forudsætninger.

Datamodel skal opbygges så simpelt som muligt med mulighed for fleksibilitet (modulær opbygning). Der skal tages udgangspunkt i Open Source-standarder/ontologier som fx BrickSchema/Real EstateCore.

IoT Lab ved Aarhus Kommune arbejder pt med at lave en datamodel. JN har været i dialog med Kristian Risager.


#### 2) Reguleringsmotoren

En fælles referencealgoritme, som styrer varmetilførslen i praksis via setpunkt til bygningernes bygningsautomatik.

Reguleringsmotoren anvender målt rumtemperatur, vejrdata, historik, tidsplaner og definerede fallback-strategier til at regulere setpunkter for fremløbstemperatur og varmekurver.

Kerneproduktet er ikke kun data og integrationer, men også en basal, fungerende styringslogik.

*[kommentarer på mødet]:*

Referencealgoritme skal udelukkende anvendes til at sende et ”prædiktiv” setpunkt til styring af fremløbstemperatur af varmesløjfer for radiator- og gulvvarmeanlæg.

Der skal være fokus på, at der haves en fallback-plan i styringsstrategi.


#### 3) Connector-laget

Standardiserede integrationer til CTS- og IoT-systemer samt eksterne datakilder.

Connector-laget gør det muligt at koble lokale bygningsinstallationer ind i en fælles ramme og reducerer afhængigheden af proprietærer løsninger.

Connector-specifikationerne fungerer som en åben kontrakt: de definerer præcist, hvilke data der skal leveres, i hvilket format og med hvilken frekvens. Det gør det transparens for leverandører at anvende løsningen i praksis.

*[kommentarer på mødet]:*

Der anvendes kendte komponenter i løsningen. Produktet kan være, at OS2 AI Heat Control kan udstille et API som kan sende og modtage data til referencealgoritmen.

Connector-laget har indbygget krav til datamodellering.


#### 4) Implementerbarhed & drift

Kommunal driftsegnethed, cybersikkerhed og lave implementeringsomkostninger.

Kerneproduktet skal ikke kun være teknisk velfunderet; det skal også kunne implementeres enkelt, driftes økonomisk og godkendes i kommunal praksis.

Kommunal driftsegnethed, cybersikkerhed og lave implementeringsomkostninger er en del af selve kerneproduktet, og ikke noget, der kommer bagefter

*[kommentarer på mødet]:*

Der skal tages stilling til NIS2 produktet, og laves en generel vurdering af, hvad der i relation til løsningen er kritisk infrastruktur (fx er indetemperaturen på et plejehjem kritisk?).

Senere i projektet skal der laves et review fra eksperter om cybersecurity af den samlede løsning ift. NIS2.

Løsningen skal kunne implementeres af flere leverandører (OS2/Jan kan hjælpe med at definere softwarearkitekturen) med følgende fokus:

- Der skal være muligt at flytte al data til anden leverandør
- OS2-fællesskabet skal være ”steward” på Github repository
- Mulighed for at data skal hostes ved OS2 med hver kommune som ”tenant”
- Ønske om fælles drift med ting/data vi vil dele. Kommuner skal selv kunne beslutte hvor data opbevares.
- Vigtigt at definition af opdateret kildekode er klar for kommende udviklingspartner (der kan inddrages erfaringer fra andre OS2-løsninger til at skærpe denne del).

**Ansvarlig**: OS2/Jan


### AD 4: Plan for dialog med markedet

#### 4.1.

Der laves en plan for dialog med markedet. Plan vil tage udgangspunkt i to steps:

Step 1: Potentielle SKI-leverandører (fx Iterator. JN drøfter det sammen med OS2-sekretariatet på møde den 10/4-2026)

Step 2: Virksomheder der potentielt kan levere del-elementer til den samlede løsning. Virksomhederne udmærker sig ved at have specifik domæne-viden (fx Neogrid, Ento, ProptechOS, ReMoni, Kiona, etc)

**Ansvarlig**: JN


#### 4.2.

Derudover overvejes det om andre aktører kan bidrage med viden til at udvikle løsningen:

- OS2 FleetOptimizer ift erfaringer med at connecte til properitære enheder
- Gate21, GovtechMidtjylland/referencebygninger og OS2IoT ift. få lavet en fælles datamodel for kommunale ejendomme
- Aalborg Kommune ift. erfaringer med navngivning af CTS (Kim Vistisen)
- Aarhus Universitet (Søren Harbo) ift. erfaringer med anvendelse af BrickSchema m.m.
- OS2 Valghalla ift. erfaringer med organisering mm
- Christian Anker Hviid, DTU ift definitioner og anvendelse af BrickSchema

JN vurderer løbende omfanget af at inddrage andre aktører i arbejdet med at skabe den bedste løsning.


#### 4.3.

Aarhus Kommune kører test med SDU på fire daginstitutioner (AI-styret, prædiktiv varmestyring). Der vurderes om projektet vil kunne bidrage med viden til OS2 AI Heat Control.


### AD 5: Næste skridt

#### 5.1.

Det blev besluttet at rykke næste møde til den 21/4 (Teams-møde erstattes af fysisk møde i Kolding). På mødet vil der være fokus på at træffe beslutninger om kravspecifikation af kerneprodukt, som kan anvendes i en formaliseret markedsdialog med potentielle leverandører.


#### 5.2.

JB hører Aarhus Kommune om hvad der gælder i SKI-aftaler (er der dynamiske indkøbsaftaler?)

**Ansvarlig**: JK


#### 5.3.

OS2-sekretariatet udarbejder bilag om non-funktionelle krav til løsningen. Bilag vedlægges projektets egen kravspecifikation.

**Ansvarlig**: AB


#### 5.3.

Der oprettes en sandkasse til OS2AIHeatControl på Github. Github anvendes til at sikre sporbarhed og transparens i udviklingsforløbet.

**Ansvarlig**: AB


### AD 6: Eventuelt

#### 6.1.

Intet at bemærke.

---
