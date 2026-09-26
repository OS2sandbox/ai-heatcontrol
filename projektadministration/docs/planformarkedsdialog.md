# Plan for markedsdialog

## Platformspartner og proces for indbydelse af udviklingspartner

**Projekt:** OS2AIHeatControl
**Dokumenttype:** Mødebilag / beslutningsoplæg
**Dato:** 2. juni 2026
**Version:** Udkast

---

## Kort anbefaling

* Gennemfør en struktureret markedsdialog med mulige platformspartnere og evt. bredere marked, før materiale til udviklingspartner færdiggøres.
* Brug markedsdialogen til at kvalificere rollefordeling, arkitektur, open source-governance, drift/DevOps, sikkerhed og indkøbsspor.
* Beslut efter dialogen, om udviklingspartner skal indbydes via dynamisk indkøbssystem/SKI-aftale eller via særskilt udbudsproces.

---

## Formål og afgrænsning

Markedsdialogen skal give projektet et bedre beslutningsgrundlag før valg af platformspartner og før indbydelse af en udviklingspartner. Dialogen skal ikke bruges til at vælge leverandør direkte, men til at kvalificere behov, rollefordeling, risici, anskaffelsesmodel og det efterfølgende materiale.

| Spor              | Formål                                                                                                                                     | Forventet output                                                                         |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| Platformspartner  | Afklare hvordan en teknisk platformspartner kan understøtte arkitektur, DevOps, open source-setup, drift, sikkerhed og teknisk governance. | Rollebeskrivelse, ansvarsfordeling, mulige leverancemodeller og krav til platform/drift. |
| Udviklingspartner | Afklare hvordan udviklingsopgaven bør formuleres, opdeles og indkøbes, så leverancen kan gennemføres iterativt og med tydeligt ansvar.     | Opgavebeskrivelse, MVP-afgrænsning, evalueringsmodel og anbefalet indkøbsspor.           |
| Indkøbsstrategi   | Afklare om anskaffelsen bedst gennemføres via dynamisk indkøbssystem, SKI-aftale eller særskilt udbud.                                     | Beslutningsnotat til styregruppen/indkøb med anbefalet proces.                           |

---

## Vigtig afgrænsning

* Deltagelse i markedsdialog giver ikke fortrinsret i en senere konkurrence.
* Eventuel viden fra dialogen, som er relevant for tilbudsgivning, skal indarbejdes eller deles i det senere materiale for at sikre ligebehandling.
* Endeligt valg af indkøbsspor bør afstemmes med indkøbsjurist/SKI og den ordregivende organisation.

---

## Rolle og ansvar

| Ansvarsområde          | Mulige opgaver for platformspartner                                                                          | Afklaring i markedsdialog                                                              |
| ---------------------- | ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------- |
| Teknisk platform       | Etablere og vedligeholde referencearkitektur, miljøer, CI/CD, komponentvalg og teknisk dokumentation.        | Skal platformspartner levere platform, rådgive om platform eller være teknisk steward? |
| Open source-governance | Opsætte repository-struktur, licensprincipper, releaseproces, issues, contributions og dokumentationskrav.   | Hvilket minimumsniveau for governance er realistisk i MVP-fasen?                       |
| DevOps og drift        | Byggelines, testmiljø, staging, deployment, monitorering, logging og driftsdokumentation.                    | Hvad skal ligge hos platformspartner, udviklingspartner og senere driftsorganisation?  |
| Sikkerhed              | Sårbarhedsscanning, adgangsstyring, logging, secrets management, backup, incident-proces og sikkerhedsbilag. | Hvilke sikkerhedskrav bør stilles i anskaffelsen, uden at låse løsningen unødigt?      |
| Leverandøruafhængighed | Standarder, dokumentation, overdragelse, open source-modeller og undgåelse af teknisk lock-in.               | Hvilke kontrakt- og dokumentationskrav er nødvendige for reel uafhængighed?            |

---

## Spørgeramme til markedsdialog

| Tema                  | Spørgsmål                                                                                                                              |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Platformrolle         | Hvilke opgaver bør ligge hos en platformspartner, og hvilke bør ligge hos udviklingspartneren eller projektejeren?                     |
| Arkitektur            | Hvilke arkitekturprincipper bør fastlægges før udviklingspartneren indbydes?                                                           |
| Open source           | Hvordan bør projektet håndtere repository, licenser, releaseproces, dokumentation, bidrag og community-governance?                     |
| DevOps                | Hvad er et passende minimumssetup for CI/CD, test, staging, produktion, monitorering og logging i MVP-fasen?                           |
| Sikkerhed             | Hvilke sikkerhedskrav er nødvendige fra start, og hvilke kan modnes undervejs?                                                         |
| Data og integrationer | Hvilke datamodeller, API-principper og integrationsmønstre bør være styrende?                                                          |
| Samarbejdsmodel       | Hvordan bør sprint, demoer, backlog, prioritering og accepttest organiseres mellem platformspartner, udviklingspartner og projektteam? |
| Indkøb                | Hvilke dele egner sig til timebaseret konsulentkøb, hvilke til opgavekøb med leveranceansvar, og hvilke til drift/platformaftale?      |
| Risici                | Hvad er de væsentligste tekniske, organisatoriske, økonomiske og kontraktmæssige risici?                                               |
| Overdragelse          | Hvilke krav skal stilles for at sikre leverandøruafhængighed og mulighed for senere drift/videreudvikling?                             |

---

## Beslutninger på mødet

* Hvilke aktører skal indbydes til markedsdialog for platformsudvikling, fx KvalitetsIT?
* Skal platformspartnerrollen være rådgivende, udførende/driftsansvarlig eller teknisk steward?
* Skal platformspartner og udviklingspartner være to adskilte roller/anskaffelser?
* Skal SKI/DIS være førstevalg, eller skal særskilt udbud forberedes parallelt?
* Hvem godkender markedsdialognotat og endelig anskaffelsesstrategi?
