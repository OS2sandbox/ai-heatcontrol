📆 _sidst opdateret: {{ site.time | date: '%B %d, %Y' }}_

# Referat :   OS2 AI Heat Control - projektgruppemøde 03.06.2026

**Status**
- [x] Mødet kalendersat
- [x] Dagsorden udarbejdet
- [x] Referat påbegyndt
- [x] Referat sendt til godkendelse
- [ ] Referat godkendt
- [ ] Referat publiceret  


## Mødefakta
  
**Mødenavn**: OS2 AI Heat Control projektgruppemøde  
**Tid**: 03.06.2026  kl. 10.00 - 12.30  
**Sted**: Ikast-Brande Kommune

#### Deltagere:
- [x] Mikkel Groot Andersen, Silkeborg Kommune, IT
- [x] Martin Hansen, Kolding Kommune
- [x] Jakob Hovgaard Kaiser, Aarhus Kommune
- [x] Anders Aschlund Bach Burkahl, Ikast-Brande Kommune
- [x] Villads Laraignou Mønsted, Gladsaxe Kommune (deltog på Teams)
- [x] Jesper Buchhardt, Silkeborg Kommune, EJD
- [x] Jan Maack Kjerbye, OS2-sekretariatet
- [x] Jakob Thøtt Nørby, 4BC

#### Afbud:
- [] Anna-Lis Berg, OS2-sekretariatet

#### Faciliteret af xxxxxxx:
- [x] Jakob Thøtt Nørby, 4BC
  
#### Observers/ Gæster
- [] 

## Møde Indhold

### Møde beskrivelse

Formålet med mødet var at følge op på seneste projektmøde, gennemgå den aktuelle handlingslog (https://github.com/OS2sandbox/ai-heatcontrol/issues) og orientere projektgruppen om oplæg på GreenInsight.

Mødet vil have fokus på at beslutte **[Reference arkitektur](https://github.com/OS2sandbox/ai-heatcontrol/blob/34-reusable-architecture-proposal)**, forberedelse og plan for dialog med Platformsspecialister, samt følge op på brugen af GitHub som fælles arbejdsrum.

### Baggrundsmateriale ((fx præsentation, styringsredskaber, mm)
- [Procesplan](https://github.com/OS2sandbox/ai-heatcontrol/blob/34-reusable-architecture-proposal/projektadministration/styring/procesplan.md)

### Dagsorden
1. Formalia     
   1. Verifikation af deltagere, mødeleder og referent
   2. Godkendelse af referat fra tidligere møde og dagsorden
2. Opfølgning:
   1. Status på igangværende aktiviteter (se [Issues]([https://github.com/OS2sandbox/ai-heatcontrol/issues](https://github.com/OS2sandbox/ai-heatcontrol/issues?q=state%3Aopen%20label%3APM)))
   2. Opfølgning på [proces- og tidsplan](https://github.com/OS2sandbox/ai-heatcontrol/blob/34-reusable-architecture-proposal/projektadministration/styring/procesplan.md)
   3. Budget og ressourcer
3. Tema 1: **Reference arkitektur, Oplæg kan ses [her](https://github.com/OS2sandbox/ai-heatcontrol/blob/34-reusable-architecture-proposal/docs/content/architecture.md)**  
4. Tema 2: **Plan for Markedsdialog**
5. Tema 3: **Godkendelse af beslutningslogs, [SDR-001](https://github.com/OS2sandbox/ai-heatcontrol/issues/36) og [ADR-001](https://github.com/OS2sandbox/ai-heatcontrol/issues/37**
6. Evt. & næste møde

#### Beslutnings og action logs
- [Link til strategisk beslutningslog](https://github.com/OS2sandbox/ai-heatcontrol/issues?q=is%3Aopen%20is%3Aissue%20label%3A%22SDR%22) 
- [Link til architectural decision records](https://github.com/OS2sandbox/ai-heatcontrol/issues?q=is%3Aopen%20is%3Aissue%20label%3A%22ADR%22) 
- link til risikolog (ikke tilgæenglig pt)

## Møde referat

### AD 1: Formalia
   - [x] Mødeleder og referent udpeget
   - [x] Referat godkendt

### AD 2: Opfølgning
 - [ ] **Status på igangværende aktiviteter**  
    1. Brug af GitHub som arbejdsplatform
      a) Generelt er det rigtig godt at komme på GitHub med projektet. Alle projektdeltagerne er kommet på. 
    2. Actions fra PM (https://github.com/OS2sandbox/ai-heatcontrol/issues?q=state%3Aopen%20label%3APM)
      a) Alle PM-issues blev gennemgået. Kommentarer og ændringer fremgår af det enkelte issue.
    4. Procesplan
      a) Procesplan følges generelt, men er p.t. lidt bagefter tidsplanen for definition af referencearkitektur og markedsdialog. Det er prioriteret at lægge mere tid i arbejdet med referencearkitekturen grundet vigtigheden af at komme rigtigt i gang.
    5. Opfølgning på budget og ressourcer
      a) Der oprettes et nyt issue til opfølgning på budget. Budgetopfølgning blev godkendt med en kommentar om, at budgettet nok er for lidt ift. udbud og markedsdialog.

### AD 3: Tema 1: **[Reference arkitektur](https://github.com/OS2sandbox/ai-heatcontrol/blob/34-reusable-architecture-proposal/docs/content/architecture.md)**  
Jan gennemgik oplæg til referencearkitektur med fokus på skalérbarhed og robusthed. 

Der var diskussioner om følgende elementer:
- Datamodel og versionering; hvem har ansvar for, at dataleverance i ønsket ontologi? Kunne det være en hybridmodel, hvor nogle leverandører har eget ejerskab over datamodellen, mens andre leverandører leverer rådata og OS2AIHC laver og vedligeholder "oversætteren"? Der oprettes et issue til fælles diskussion af setup, og ende med en risikovurdering
- OS2IoT er pt baseret på push, men burde måske være pull-baseret request for, at OS2AIHC er i bedre kontrol over dataleverance. Beslutningen ligger hos OS2IoT-styregruppen. Issue (feature-request) oprettes. Datakilde fra OS2IoT. Der skal etableres en dialog med OS2IoT.

### AD 4: Tema 2: **Markedsdialog**
Udsættes til et kommende projektmøde på Teams. Møde er programsat til den 16/6 kl. 11.00

### AD 5: Tema 3: **Godkendelse af beslutningslogs, [SDR-001](https://github.com/OS2sandbox/ai-heatcontrol/issues/36) og [ADR-001](https://github.com/OS2sandbox/ai-heatcontrol/issues/37)**
Udsættes til et kommende projektmøde på Teams. Møde er programsat til den 16/6 kl. 11.00

### AD 6: Evt. & næste møde 
Der indkaldes til nyt møde.
 
  ---
