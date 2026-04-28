# Beslutningslog (Git-skabelon)

📆 _sidst opdateret: {{ site.time | date: '%B %d, %Y' }}_

## Formål

Denne README beskriver den fælles skabelon for registrering af væsentlige beslutninger i produktet. Skabelonen kan anvendes til arkitekturbeslutninger, strategiske beslutninger og operationelle beslutninger.

Beslutninger registreres som GitHub Issues, så beslutningsgrundlag, kontekst, konsekvenser og effektuering kan dokumenteres og spores over tid.

---

## Issue metadata (GitHub-standard)

```yaml
name: Beslutningslog
about: Struktureret beskrivelse af en væsentlig beslutning i produktet
title: "[Titel]"
labels: ""
assignees: ""
```

---


## Statusværdier

| Status | Betydning |
|---|---|
| Forslag | Beslutningen er foreslået, men endnu ikke godkendt. |
| Accepteret | Beslutningen er godkendt og gældende. |
| Erstattet | Beslutningen er ikke længere gældende og er erstattet af en ny beslutning. |
| Afvist | Beslutningen er afvist og skal ikke effektueres. |

---

## Beslutningstyper

| Type | Beskrivelse |
|---|---|
| ADR | Architecture Decision Record – arkitekturbeslutning. |
| SDR | Strategic Decision Record – strategisk beslutning. |
| ODR | Operational Decision Record – operationel beslutning. |

---

## Anbefalet arbejdsgang

1. Opret et nyt GitHub Issue med skabelonen.
2. Udfyld beslutningens metadata.
3. Beskriv kontekst, beslutning, konsekvenser og risici.
4. Angiv ansvarlig for effektuering.
5. Tilføj relevante links til issues, pull requests eller dokumentation.
6. Opdater status, når beslutningen ændrer sig.
