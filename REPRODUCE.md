# How this repository was made (Formosa)

This file is written by the build on 2026-11-05, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Gobierno de la Provincia de Formosa (www.formosa.gob.ar) | <https://www.formosa.gob.ar/miprovincia/simbolosprovinciales/constitucion> | 2026-10-30 | Official legal texts of the province, published by its government for public consultation. Argentina's copyright law (Ley 11.723) has no express exclusion for them; laws are public acts of government, binding on everyone once officially published (Código Civil y Comercial, art. 5). The source states no restriction on reuse. Reproduced with attribution, following the official text. |
| Gobierno de la Provincia de Formosa, Defensa del Consumidor y Usuario | <https://www.formosa.gob.ar/defensaconsumidor/legislacion> | 2026-11-05 | Official provincial legal text made available for public consultation; no reuse restriction stated on the source page. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `constitucion` | Constitución de la Provincia de Formosa | 1 | 2025-09-08 to 2025-09-08 |
| `ley-1480-defensa-consumidor` | Procedimiento administrativo para la defensa de los derechos del consumidor y usuario | 1 | 2026-11-05 to 2026-11-05 |

The build made 2 commits:

| Commits | Kind |
| ---: | --- |
| 2 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futuro`: laws not yet in force on 2026-11-05.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 3 tags.

## Dates

Each commit is dated at noon (America/Argentina/Cordoba) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Código Civil y Comercial de la Nación, art. 5: "Las leyes rigen después del octavo día de su publicación oficial, o desde el día que ellas determinen", counted under art. 6 (the day of publication is excluded), so a law without its own vigencia clause is in force from the ninth day after its publication in the provincial Boletín Oficial (before 1 August 2015, Código Civil art. 2 as replaced by Ley 16.504, to the same effect). A law's own vigencia clause overrides the rule. https://servicios.infoleg.gob.ar/infolegInternet/anexos/235000-239999/235975/texact.htm

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `3087803aa80946feb1821cc3d5a108e891a25c6dbcddd84eadf1e4984dc216ef` (201763 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `35388bee5aa05369f7da68f5a8fa015ea8d442b8`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

Not yet run for this build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Constitution: the provincial government's PDF of the Constitución de la Provincia de Formosa (sanctioned and promulgated by the Convención Constituyente on 5 September 2025; published in Boletín Oficial N° 12782 of 8 September 2025; cláusula transitoria 1ª: "La presente Constitución entrará en vigencia a partir de su publicación"), shown as enacted, dated 8 September 2025. The constitution of 1991/2003 it replaced is not shown.
- Laws are not built: no official source of per-law texts was found (the Legislatura site has news only).
- Units: the heading (encabezado: the preamble and everything before Art. 1) and one file per article, holding the article and everything printed after it up to the next article (section headings, the transitional clauses and the final provision after the last article). Nothing is dropped. One paragraph per line, spacing normalised.
- Ley 1480: The official PDF and its departmental listing give no sanction, publication, commencement, consolidation or amendment date. The source gives no date at all; 5 November 2026 is the retrieval-day fallback for this oldest available current-text version, not a proven legislative commencement date.
- Ley 1480 is a single-file current-text act: all source text is retained in order, excluding only the seven printed page numbers; whitespace is normalized. The source supplies no earlier versions.
- Ley 1480: source images 0, referenced images 0, omitted images 0.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- A model (Claude) wrote the fetch and parse code and chose which norms to include; it wrote no law text. Every word of law comes from the provincial source's own texts.
- A model selected the official source and metadata. Deterministic PDF extraction supplies all law wording, without OCR or model text edits.
