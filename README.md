# M. Faizan Chaudhary · Data Science Portfolio

A [Quarto](https://quarto.org) book that collects my data science work from the
Master Smart Data Science at ENSAI. Every chapter is rendered from source and
downloads its data by code.

| Chapter | Project | Language |
|---|---|---|
| `chapters/01-EDA.qmd` | Urban trees of Saint-Germain-en-Laye (EDA) | R |
| `chapters/02-tgv-delays.qmd` | Late again? TGV delays (data visualisation) | R (original app: Python/Bokeh) |
| `chapters/03-agentic-phm.qmd` | Agentic AI for predictive maintenance (Safran) | R (project: Python) |
| `chapters/04-coursework.qmd` | ML and R labs | text |
| `chapters/semester-2.qmd`, `semester-3.qmd` | placeholders for later courses | |

## Build it

The R version (`.r-version`) and package versions (`uvr.lock`) are pinned with
[uvr](https://github.com/nbafrank/uvr).

```bash
uvr sync                 # install the locked packages into .uvr/library
quarto preview           # live preview while editing
quarto render            # build the book into _book/
```

On Debian/Ubuntu, some packages need system libraries:

```bash
sudo apt-get install -y libabsl-dev libfontconfig1-dev libfreetype6-dev libfribidi-dev libharfbuzz-dev
```

## Layout

```
_quarto.yml      book config: chapters, parts, output format
_brand.yml       colours and fonts
styles.scss      layout tweaks (project cards, stat tiles, code blocks)
index.qmd        home page          about.qmd   CV-style about page
chapters/        one .qmd per project
data/raw/        open data, downloaded by the chapters on first render
data/safran/     evaluation results copied from the Safran project
references.bib   citations
_freeze/         cached chapter results (commit it)
```

## Data

- Urban trees: Ville de Saint-Germain-en-Laye, data.gouv.fr.
- TGV punctuality: SNCF open data (ODbL), via data.gouv.fr.
- Safran results: produced by the evaluation scripts in the
  `ensai_agentic_PHM` project (synthetic OpenDeckSMR data).

Files in `data/raw/` are only downloaded if missing. Delete them to fetch fresh
copies; the SNCF files are updated monthly, so the numbers can change.
