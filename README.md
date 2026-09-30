# Python for Data Science: Master in Finance (PGE 5)

Course materials by [Andrea Guido](https://andreaguido.github.io), Paris School of Business.

Four sessions of 3h30 for beginner-to-intermediate Python users. One question runs through the course: **could the bank have seen default coming?** We work with a real dataset of 30,000 credit card clients and take it from raw file to defensible answer.

| Session | Topic | Slides | Notebook |
|---|---|---|---|
| 1 | Import & inspect: load the raw file and list what looks wrong | [PDF](slides/session1_slides.pdf) | `session1.ipynb` |
| 2 | Clean & describe: turn each oddity into a documented decision, first patterns | [PDF](slides/session2_slides.pdf) | `session2.ipynb` |
| 3 | Test: chi-square, t-test / Mann–Whitney, linear regression | [PDF](slides/session3_slides.pdf) | `session3.ipynb` |
| 4 | Present & defend: how much do your choices drive your answers? | [PDF](slides/session4_slides.pdf) | |

## Getting started

1. Install Python and the packages below (see `setup_guide.html` for a step-by-step guide).
2. Download this repository (green **Code** button → **Download ZIP**) and unzip it.
3. Open the notebooks **from this folder**: they read the data with paths like `data/raw/...`.
4. Session 3 starts from `data/clean/clients_clean.csv`, which you create at the end of Session 2.

```
pip install -r requirements.txt
```

## Data

*Default of Credit Card Clients* (Taiwan, 2005), UCI Machine Learning Repository, dataset #350, licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Codebook, known traps, and research questions: [`data/README.md`](data/README.md).

Yeh, I-C. & Lien, C-H. (2009). The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients. *Expert Systems with Applications*, 36(2), 2473–2480.
