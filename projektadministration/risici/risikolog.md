# Risikolog

En risikolog kan opbygges som en simpel Markdown-tabel.

Bidragydere skal have en GitHub-konto og være bekendte med, hvordan man foreslår ændringer via pull requests (PRs).

Beregningerne skal foretages manuelt.

---

## Simpelt eksempel på en risikolog i Markdown

| Risiko-ID | Risikotitel | Beskrivelse | Sandsynlighed (S: 1-5) | Konsekvens (K: 1-5) | Risikoscore (S x K) | Status/ansvarlig | Afbødende handling |
| :---: | :--- | :--- | :---: | :---: | :---: | :--- | :--- |
| OS-001 | ... | ... | ... | ... | ... | ... | ... |
| OS-002 | ... | ... | ... | ... | ... | ... | ... |

---

## Visuel nøgle baseret på risikoscore

Emoji angiver det beregnede risikoniveau:

- **🔴 Høj risiko (score 15-25):** Kræver øjeblikkelig handling og synlighed hos ledelse/styregruppe.
- **🟡 Middel risiko (score 8-14):** Kræver aktiv afbødende handling.
- **🟢 Lav risiko (score 1-7):** Overvåges, eller risikoen er allerede afbødet/accepteret.

## Beregning

**Risikoscore** beregnes som:

> Sandsynlighed (1-5) x Konsekvens (1-5)

- **Høj risiko:** 15-25
- **Middel risiko:** 8-14
- **Lav risiko:** 1-7
