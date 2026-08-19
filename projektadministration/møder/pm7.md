📆 _sidst opdateret: {{ site.time | date: '%B %d, %Y' }}_

# Referat :   OS2 AI Heat Control - projektgruppemøde 16.06.2026

**Status**
- [x] Mødet kalendersat
- [x] Dagsorden udarbejdet
- [x] Referat påbegyndt
- [x] Referat sendt til godkendelse
- [x] Referat godkendt
- [x] Referat publiceret  


## Mødefakta
  
**Mødenavn**: OS2 AI Heat Control projektgruppemøde  
**Tid**: 16.06.2026  kl. 11.00 - 12.00  
**Sted**: Teams

#### Deltagere:
- [x] Martin Hansen, Kolding Kommune
- [x] Jakob Hovgaard Kaiser, Aarhus Kommune (delvist)
- [x] Villads Laraignou Mønsted, Gladsaxe Kommune (deltog på Teams)
- [x] Jesper Buchhardt, Silkeborg Kommune, EJD
- [x] Jakob Thøtt Nørby, 4BC

#### Afbud:
- [ ] Anna-Lis Berg, OS2-sekretariatet
- [ ] Anders Aschlund Bach Burkahl, Ikast-Brande Kommune
- [ ] Mikkel Groot Andersen, Silkeborg Kommune, IT
- [ ] Jan Maack Kjerbye, OS2-sekretariatet

#### Faciliteret af:
- [x] Jakob Thøtt Nørby, 4BC
  
#### Observers/ Gæster:
- [ ] 

## Møde Indhold

### Møde beskrivelse

Formålet med mødet var at følge op på seneste projektmøde og gennemgå den aktuelle handlingslog med særligt fokus på de punkter, der ikke blev nået på sidste møde.

Mødet havde især fokus på:

- Plan for markedsdialog
- Godkendelse af beslutningslogs
- Opfølgning på etablering af faggrupper
- Afklaring af næste skridt i forhold til projektorganisering og udbudsproces

Formålet med mødet var at følge op på seneste projektmøde, gennemgå den aktuelle handlingslog (https://github.com/OS2sandbox/ai-heatcontrol/issues) med særligt fokus på de punkter der ikke blev nået på sidste møde omhandlende **Plan for Markedsdialog** og **Godkendelse af beslutningslogs**.

### Baggrundsmateriale ((fx præsentation, styringsredskaber, mm)
- [Plan for markedsdialog](https://github.com/OS2sandbox/ai-heatcontrol/blob/markedsdialog/projektadministration/docs/planformarkedsdialog.md)

### Dagsorden
1. Formalia     
   1. Verifikation af deltagere, mødeleder og referent
   2. Godkendelse af referat fra tidligere møde og dagsorden
2. Opfølgning:
   1. Status på igangværende aktiviteter (se [Issues]([https://github.com/OS2sandbox/ai-heatcontrol/issues](https://github.com/OS2sandbox/ai-heatcontrol/issues?q=state%3Aopen%20label%3APM)))
3. Tema 1: **Plan for Markedsdialog**
4. Tema 2: **Godkendelse af beslutningslogs, [SDR-001](https://github.com/OS2sandbox/ai-heatcontrol/issues/36) og [ADR-001](https://github.com/OS2sandbox/ai-heatcontrol/issues/37)**
5. Evt. & næste møde

#### Beslutnings og action logs
- [Link til strategisk beslutningslog](https://github.com/OS2sandbox/ai-heatcontrol/issues?q=is%3Aopen%20is%3Aissue%20label%3A%22SDR%22) 
- [Link til architectural decision records](https://github.com/OS2sandbox/ai-heatcontrol/issues?q=is%3Aopen%20is%3Aissue%20label%3A%22ADR%22) 
- link til risikolog (ikke tilgæenglig pt)

## Møde referat

### AD 1: Formalia
   - [x] Mødeleder og referent udpeget
   - [x] Referat godkendt fra seneste møde

### AD 2: Opfølgning
**Status på igangværende aktiviteter**
Projektgruppen gennemgik status på relevante åbne [issues](https://github.com/OS2sandbox/ai-heatcontrol/issues?q=state%3Aopen%20label%3APM) fra projektmøderne. Særligt blev følgende punkter drøftet:

  1) Etablering af faggrupper
Det blev præciseret, at etablering af faggrupper først og fremmest handler om at forstå brugernes oplevelse og behov i praksis. Faggrupperne skal bidrage til, at løsningen ikke alene udvikles ud fra tekniske krav, men også ud fra den virkelighed, som driftspersonale og slutanvendere står i. Et eksempel blev nævnt: En pedel kan have behov for at få synliggjort, hvordan varmeanlægget styres, og hvorfor systemet regulerer, som det gør. Det er derfor vigtigt, at faggrupperne kan bidrage med viden om arbejdsgange, forståelsesbehov, brugeroplevelse og praktisk implementering.

  2) Fælles indkøb af LoRaWAN-sensorer
Punktet om fælles indkøb af LoRaWAN-sensorer blev ikke behandlet i dybden på mødet. Det blev aftalt, at punktet tages op på næste møde.
Projektorganisering
Der skal udarbejdes en opdatering af projektorganiseringen, hvor der sondres mellem styregruppe og koordinationsgruppe. Partnerne opfordres til at melde relevante deltagere ind til de to grupper.

  3) Udbudsproces
Jakob Nørby tager kontakt til Aarhus Kommune / Jakob Kaiser med henblik på at afklare mulighed for bistand fra en udbudsjurist til at drive eller understøtte udbudsprocessen.

### AD 3: Tema 1: **Plan for markedsdialog**
Projektgruppen drøftede den videre plan for markedsdialog.

Det blev fremhævet, at markedsdialogen skal bidrage til at kvalificere projektets videre arbejde med krav, arkitektur, datamodel og udbudsproces. Markedsdialogen skal samtidig gennemføres på en måde, der ikke kompromitterer et senere udbud eller valg af leverandør.

Det blev drøftet, at grundelementerne i OS2 AI Heat Control bør ses i sammenhæng med et bredere potentiale for automatisering mellem systemer. På sigt kan der ligge en stor gevinst for den kommunale bygningsejer i, at systemer i højere grad kan kobles sammen, udveksle data og understøtte automatiserede arbejdsgange på tværs af bygninger, tekniske installationer og kommunale driftssystemer.

Markedsdialogen bør derfor ikke kun handle om den konkrete styringsløsning, men også om hvordan OS2 AI Heat Control kan indgå i en mere sammenhængende digital infrastruktur for kommunal bygningsdrift.

Det blev desuden bemærket, at Jan Maack Kjerbye fra OS2 bør indgå i den videre markedsdialog. Jan kan bidrage med viden om open source-udvikling, arkitektur, governance og OS2’s erfaringer fra andre projekter.

Foreløbige fokuspunkter for markedsdialogen:
- Hvordan markedet vurderer projektets grundelementer
- Hvordan leverandører ser muligheder og begrænsninger i en åben, OS2-forankret løsning
- Hvordan løsningen kan understøtte automatisering mellem systemer
- Hvordan connector-lag, datamodel og integrationsarkitektur bør udformes
- Hvordan løsningen kan implementeres og driftes i kommunal praksis
- Hvilke krav der bør stilles til open source, dokumentation, cybersikkerhed og leverandøruafhængighed
- Hvordan projektet bedst tilrettelægger udbud eller valg af udviklingspartner

### AD 4: Tema 2: **Godkendelse af beslutningslogs, [SDR-001](https://github.com/OS2sandbox/ai-heatcontrol/issues/36) og [ADR-001](https://github.com/OS2sandbox/ai-heatcontrol/issues/37)**
Projektgruppen gennemgik de to beslutningslogs: `SDR-001` og `ADR-001`

Begge beslutningslogs blev godkendt.

Der var dog en kommentar til ADR-001 om, at afsnittet “Effektuering” skal opdateres. Godkendelsen sker således med forbehold for, at denne opdatering indarbejdes.


### AD 5: Evt. & næste møde 
**Eventuelt**

Der blev ikke rejst yderligere punkter under eventuelt.

**Næste møde**

På næste møde behandles blandt andet:
- Fælles indkøb af LoRaWAN-sensorer
- Opdateret projektorganisering med styregruppe og koordinationsgruppe
