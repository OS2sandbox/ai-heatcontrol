# Risikolog

| Risiko-ID | Risikotitel | Beskrivelse | Relaterede issues | Sandsynlighed (S: 1-5) | Konsekvens (K: 1-5) | Risikoscore (S x K) | Status/ansvarlig | Afbødende handling |
| :---: | :--- | :--- | :--- | :---: | :---: | :---: | :--- | :--- |
| OS-001 | 🟡 Uklar projektorganisering | Der er risiko for uklare roller, ansvar og beslutningsmandat mellem styregruppe, koordinationsgruppe, OS2-sekretariat og projektleder. | [#50 Projektorganisering](https://github.com/OS2sandbox/ai-heatcontrol/issues/50) | 3 | 4 | 12 | Åben / Styregruppe | Afklare organisering, kommissorium, mandat, mødefrekvens og deltagerkreds for styregruppe og koordinationsgruppe. |
| OS-002 | 🔴 Manglende commitment fra kommuner og linjeledelse | Der er risiko for, at projektdeltagere eller kommunernes linjeledelse ikke prioriterer projektet tilstrækkeligt. Det kan medføre manglende betalinger, lav mødedeltagelse, begrænsede ressourcer, manglende bidrag til udførelse og svag forankring i de deltagende organisationer. | [#50 Projektorganisering](https://github.com/OS2sandbox/ai-heatcontrol/issues/50) | 4 | 5 | 20 | Åben / Kommuner der har givet tilsagn | Sikre tydelig ledelsesforankring, afklare forventninger til deltagelse og betaling, beskrive kommunernes forpligtelser og få bekræftet mandat fra relevante linjeledelser. |
| OS-003 | 🟡 Forsinket udbudsproces | Udbudsprocessen kan blive yderligere forsinket, hvis der ikke hurtigt afklares ressourcer, indkøbsspor, markedsdialog og juridiske/udbudsmæssige rammer. | [#31 Udbudsproces / SKI / markedsdialog](https://github.com/OS2sandbox/ai-heatcontrol/issues/31) | 4 | 2 | 8 | Åben / Styregruppe | Afklare om interne udbudsressourcer kan anvendes, og om der skal tilknyttes ekstern specialistbistand. |
| OS-004 | 🔴 Budgetusikkerhed | Der er risiko for, at budgettet ikke afspejler ambitionen for projektets rammer for Open Source og digital suverænitet. | [#57 Tilkøb af ekstern Gitforvalter-bistand](https://github.com/OS2sandbox/ai-heatcontrol/issues/57), [#31 Udbudsproces](https://github.com/OS2sandbox/ai-heatcontrol/issues/31) | 4 | 5 | 20 | Åben / Styregruppe | Gennemgå budgettet op mod næste fase og træffe beslutning om prioritering af midler. |
| OS-005 | 🟢 Manglende Gitforvalter / teknisk forvaltning | Projektet kan mangle løbende teknisk forvaltning af GitHub, issues, pull requests, dokumentation, open source-governance og sikkerhed. | [#57 Tilkøb af ekstern Gitforvalter-bistand](https://github.com/OS2sandbox/ai-heatcontrol/issues/57), [#45 GitHub assignees / rettigheder](https://github.com/OS2sandbox/ai-heatcontrol/issues/45), [#46 GitHub Pages deployment](https://github.com/OS2sandbox/ai-heatcontrol/issues/46) | 1 | 3 | 3 | Åben / Styregruppe | Beslutte om der skal tilkøbes ekstern Gitforvalter-bistand, hvornår den igangsættes, og hvem der har mandat til opstart. |
| OS-006 | 🟡 Uafklaret datamodel og dataleverance | Der er risiko for uklarhed om ansvar for datamodel, ontologi, versionering og dataleverance fra OS2IoT eller andre datakilder. | [#43 Datamodel og versionering](https://github.com/OS2sandbox/ai-heatcontrol/issues/43), [#44 OS2IoT dataleverance](https://github.com/OS2sandbox/ai-heatcontrol/issues/44) | 3 | 4 | 12 | Åben / Koordinationsgruppe | Afklare ansvar for datamodel, versionering, oversættelseslag og dataleverance som del af kravspecifikation og teknisk arkitektur. |
| OS-007 | 🟡 Leverandørafhængighed | Projektet kan blive afhængigt af én leverandør, én platform eller proprietære løsninger, hvis krav til åbenhed, dokumentation og teknisk forvaltning ikke fastholdes. | [#31 Udbudsproces / leverandørdialog](https://github.com/OS2sandbox/ai-heatcontrol/issues/31), [#57 Gitforvalter-bistand](https://github.com/OS2sandbox/ai-heatcontrol/issues/57) | 3 | 3 | 9 | Åben / Styregruppe | Fastholde krav om åben leverancemodel, åbne standarder, dokumentation, exit-strategi og leverandøruafhængighed. |

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

Jeg har sat den til **S=4, K=5, score 20**, fordi manglende commitment potentielt kan ramme både betaling, fremdrift, bemanding, beslutninger og realisering.
