# Governancerapport for OS2 AI Heat Control

> **📄 Dokumentinformation**  
> **Version for anvendt governancerapport:** 1.1.0  
> **Dato for udfyldelse:** [14-08-2026]  
> **Udfyldt af:** [Jakob Thøtt Nørby]  
> **Link til Git organisation:** [https://github.com/OS2sandbox/ai-heatcontrol]  

## RELEVANS

| #   | Krav                                          | Produktniveau | Retningslinjer                                                                                                        | Efterlevet?   | Dokumentation      |
| --- | --------------------------------------------- | --------------| ----------------------------------------------------------------------------------------------------------------------|---------------|--------------------|
| R1  | Løsningen skaber lokal værdi                  | sandkasse     | Beskriv den konkrete værdi løsningen skaber i organisationen. F.eks. økonomisk, organisatorisk eller brugerrelateret. | Ja            | Værdien er reducerede omkostninger til energi og bidrag til CO2-reduktioner | 
| R2  | Løsningen er accepteret af lokal linjeledelse | 2             | Beskriv eller henvis til en formel accept fra ledelse hos initiativtagerne til løsningen.                             | ?             |
| R3  | Løsningen har fælles offentligt potentiale    | 2             | Redegør for hvordan løsningen kan bruges på tværs af kommuner og/eller offentlige myndigheder.                        | Ja            | Det er beskrevet hvordan løsningen skal kunne skalere på tværs af offentlige bygninger |
| R4  | Ophæng til nationale strategier er til stede  | 3             | Henvis til relevante strategier og forklar hvordan løsningen understøtter disse.                                      | Ja            | KL har udgivet en ny [digitaliseringsstrategi 2026-2030](https://www.kl.dk/oekonomi-og-administration/digitalisering-og-teknologi/politik-og-strategi/kommunernes-digitaliseringsstrategi-2026-2030), hvor et af de fem spor omhandler at accelerer den grønne omstilling med digitale løsninger |

## FORMKRAV

| #   | Krav                                          | Produktniveau | Retningslinjer                                                                                                        | Efterlevet?   | Dokumentation      |
| --- | --------------------------------------------- | --------------| ----------------------------------------------------------------------------------------------------------------------|---------------|--------------------|
| F1  | Alt kildekode til projektet udvikles synligt og aktivt i et repositorie og versionskontrolsystem, anvist af OS2 | sandkasse | Upload al kildekode i et offentligt OS2 repository med aktiv versionshistorik. | Ja     | Repository findes her: https://github.com/OS2sandbox/ai-heatcontrol |
| F2  | Open Source licenskriterier overholdes                                                                          | sandkasse | Angiv hvilken OSI-godkendt licens projektet bruger. OS2 standard er MPL 2.0 | Delvist    | Proces-dokumentation og issue-trackere kører under [CC-BY-SA-4.0 license](https://creativecommons.org/licenses/by-sa/4.0/deed.en). Andre licenstyper afventer til der kommer kode
| F3  | Udbudsregler og alm. lovformlighed er overholdt                                                                 | sandkasse | Bekræft at udbudspligt er overholdt eller redegør for undtagelse. Vedlæg evt. beslutningsnotat.| I gang / afventer | Der er indgået kontrakt med ekstern projektleder. Dokumentering sker delvist via Github og NextCloud. Udbudsproces for udvikling er igangsat. Som fælles kommunalt fællesskab/forening er vi forpligtet til at overholde journaliseringspligten – hvordan håndterer vi det? |
| F4  | Der er tænkt på sikkerheden i løsningen                                                                         | sandkasse | Beskriv hvordan sikkerhed er indtænkt i design, kode og drift – f.eks. kryptering, adgangsstyring. | Afventer| |
| F5  | Løsningens formål og værdi er beskrevet                                                                         | sandkasse | Henvis til dokumentation (f.eks. README) hvor formål og målgruppe fremgår.    | Ja |https://github.com/OS2sandbox/ai-heatcontrol/blob/main/README.md| Ja ||
| F6  | Kildekoden er overdraget og er placeret under OS2's kontrol                                                     | 1         | Bekræft og link til det officielle repository i OS2s versionskontrol.                     | Afventer - men i planen | Der udarbejdes et overdragelsesdokument i samarbejde med OS2-sekretariet når man går fra projekt til produkt |
| F7  | Alt dokumentation til projektet udarbejdes med og overholder OS2s standardskabelon for dokumentation.           | 1         | Brug OS2’s standard template til dokumentation. [Documentation template for OS2 projects](http://github.com/OS2offdig/os2-docs-template) | Ja | Se projektets repository
| F10 | OS2's kommunikationskanaler anvendes (OS2.eu)                                                                   | 1         | Bekræft og link til omtale på f.eks. os2.eu, nyhedsbrev eller andet. | Ja | https://os2sandbox.github.io/ai-heatcontrol/ |
| F11 | Der anvendes offentlig issue-tracking anvist af OS2, hvor der tydeligt henvises til specifikke kodeændringer    | 1         | Henvis til f.eks. Issues, hvor opgaver er koblet til pull-requests/commits. | Ja | https://github.com/OS2sandbox/ai-heatcontrol/issues |
| F12 | Der er kun en version af core koden                                                                             | 2         | Bekræft at der kun findes én ‘main’ version og at den er aktivt vedligeholdt. | Nej | Maintainer-rolle er ikke besat|
| F13 | Der er udarbejdet præsentationsmateriale af løsningen                                                           | 2         | Link til f.eks. slides, brochurer eller andet introduktionsmateriale. | Ja| Se mere [her](https://www.os2.eu/web/content/15382?unique=6abf2b95a039a69c7090565dffe0b06f9a9eac00&download=true) og https://www.os2.eu/os2aiheatcontrol  |
| F14 | Der er udarbejdet kommunikationsmateriale til strategisk niveau                                                 | 2         | F.eks. businesscase, one-pager til direktionsniveau og præsentation til udvalg. | Nej ||
| F15 | Best practice for implementering i organisationen dokumenteres                                                  | 2         | Angiv implementeringsvejledning, erfaringsopsamling eller cases.                                  | Nej| |
| F16 | Teknisk dokumentation indeholder best practice for kodestandarder i forhold til de anvendte teknologier         | 2         | Beskriv Hvilke kodestandarder projektet følger. Evt. med links til eksterne guides og supplerende retningslinjer. | Nej| |
| F17 | Drifts og vedligeholdelses setup er beskrevet                                                                   | 2         | Redegør for driftspartner(e), ansvar og finansiering. Hvem drifter, hvem vedligeholder og hvem koordinere. Beskriv også Hvordan kører løsningen? (on-prem, cloud, container, SaaS). Hvilke komponenter indgår? (fx databaser, API’er, microservices). Hvilke værktøjer bruges til monitorering, deployment og backup. | Nej | |
| F18 | Rammearkitekturen og standarder er fulgt og afvigelser er forklaret                                             | 2         | Beskriv om/hvordan løsningen følger fællesoffentlig rammearkitektur – eller forklar hvorfor ikke. | Nej | |
| F19 | Løsningen er leveret i et containerformat f.eks. docker (anbefaling)                                            | 2         | Angiv om løsningen tilbydes i en containeriseret version som definerer hvordan applikationen bygges og køres. | Nej | |
| F20 | Uddannelsesmateriale er udarbejdet (anbefaling)                                                                 | 2         | Henvis til manual, brugervejledning eller andet brugerrelateret materiale. | Nej | |
| F21 | Politisk kommunikation er udarbejdet (Lokal + Omverden)                                                         | 3         | Angiv indhold der kan bruges i politiske fora – f.eks. beslutningsoplæg eller pressemeddelelse. | Nej | |
| F22 | Procesplan + procesansvar for driftsimplementering er udarbejdet                                                | 3         | Tilføj en implementeringsplan med ‘hvem gør hvad hvornår’. | Nej | |

## STRATEGISK SAMMENHÆNG

| #   | Krav                                                                                             | Produktniveau | Retningslinjer                                             | Efterlevet?   | Dokumentation      |
| --- | ------------------------------------------------------------------------------------------------ | ------ | ---------------------------------------------------------------------------------- |---------------|--------------------|
| S1  | Produktet har en kobling til OS2's strategi                                                      | 1      | Beskriv hvordan produktet understøtter tværoffentlige behov, deling og fællesskab. | Ja | Entreprise arkitekt er inddraget tidligt i udviklingen af produktet, og inddrages ligeledes løbende for at inddrage viden og kobling til andre OS2-projekter. Derudover er der et fagligt fokus på at skabe et fælles fundamentet for offentlige bygninger for at kunne skalere løsninger effektivt og robust. |
| S2  | Løsningen understøtter innovation og open source                                                 | 1      | Angiv hvordan open source-værdier og nyskabelse er tænkt ind.                      | Ja | Der arbejdes på at (gen)anvende Open Source komponenter fra andre produkter (fx GPS Connector). Markedet for AI-varmestyring er fastlåst for offentlige ejendomme, da omkostningerne til kommercielle aktører overstiger gevinsten for den offentlige bygningsejer. Årsagen er et stort vedligeholdelsesarbejde for de kommercielle aktører og risici forbundet hermed. Disse omkostninger og risici vil projektet reducere, så markedet kan fokusere på at lave kost-effektive, robuste løsninger hvor initial- og vedligeholdelsesomkostningerne kan holdes på et minimum. 
| S3  | Produktets (forventlige) kobling til OS2's mission, vision og strategi er beskrevet              | 2      | Angiv hvor produktet matcher med OS2's formål og indsatser.                        | Ja |
| S4  | Der er udarbejdet en vision og strategi for produktet                                            | 2      | Beskriv produktvision og strategiske mål.                                          | Ja |
| S5  | Produktets kobling til og overensstemmelse med OS2's vision og strategi er tilstede og beskrevet | 3      | Forklar hvordan løsningen passer ind i OS2’s overordnede værdisæt og visioner.     | Nej |

## GOVERNANCE

| #   | Krav                                                                               | Produktniveau | Retningslinjer                                                        | Efterlevet?   | Dokumentation      |
| --- | ---------------------------------------------------------------------------------- | ------------- | --------------------------------------------------------------------- |---------------|--------------------|
| G1  | Produktet er oprettet i OS2's porteføljestyring                                    | 1           | Produktet er oprettet på OS2s hjemmeside og indgår i årshjul. Dette koordineres med sekretariatet i OS2. | Ja |
| G2  | Der koordineres løbende med OS2-sekretariatet                                      | 1           | Bekræft, evt. med årshjul/datoer/mails for koordinering.                      | Ja | Der er kalendersat løbende TEMA-møder med sekretariatet, bl.a. 14/8-26, 28/8-26 og 11/9-26.
| G3  | Der er udpeget en projektleder/tovholder                                           | 1           | Navngiv og beskriv rolle og opgaver.             | Ja | Ekstern projektleder (Jakob Thøtt Nørby) er udpeget, og der er lavet kontrakt med ham |
| G4  | Bestyrelsen er orienteret                                                          | 1           | Vedlæg dokumentation for orientering.                                | ? | |
| G5  | Bestyrelsen har godkendt produktet                                                 | 2           | Vedlæg dokumentation for godkendelse.                                 | ? | |
| G6  | Der er nedsat en styregruppe                                                       | 2           | Beskrivelse af styregruppen og roller/ansvar/opgaver.                           | Nej | Der efterlyses de rette kompetencer og beslutningsmandat pt
| G7  | Der er nedsat en koordinationsgruppe (anbefaling)                                  | 2           | Beskrivelse af koordinationsgruppen og roller/ansvar/opgaver.                       | Nej | Der efterlyses de rette kompetencer og beslutningsmandat pt
| G8  | En projektmodel anvendes og er dokumenteret (anbefaling)                           | 2           | Beskriv den anvendte projektmodel eller metode.                             | Nej | |
| G9  | Review af kode foretages af tredjepart (anbefaling)                                | 2           | Angiv hvilken ekstern part som udfører eller har udført review. Link til processbeskrivelse samt revisionsrapporter.| Nej | |
| G10 | Der er udarbejdet en tilslutningserklæring til sikring af økonomi (anbefaling)     | 2           | Vedlæg eller henvis til dokument for tilslutning og økonomi.          | Nej ||
| G11 | Bestyrelsen har godkendt styregruppen                                              | 3           | Vedlæg dokumentation for beslutning.                                   | ?||
| G12 | Bestyrelsen er repræsenteret i styregruppen                                        | 3           | Angiv hvilket medlem som deltager på vegne af bestyrelsen.                | ? ||
| G13 | Der foreligger en aftale der sikrer økonomi til koordinering og videreudvikling    | 3           | Vedlæg eller beskriv finansieringsaftalen.                            | ? ||
| G14 | Der er etableret et fagligt fællesskab bag løsningen hvor erfaringer kan udveksles | 3           | Henvis til brugerforum og/eller årshjul for aktiviteter.          | Nej ||

<!-- END REPORT TEMPLATE -->
