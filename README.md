# Diamond Pricing: Exploratory Data Analysis

Project from the Google Advanced Data Analytics Professional Certificate. Applying the six-phase EDA framework (Discover, Structure, Clean, Join, Validate, Present) to a real dataset of 53,940 diamonds.

## Key finding

Diamonds with the best clarity grade (IF) average a LOWER price than diamonds with the worst clarity grade (I1): $2,871 vs $3,927. That looks backwards until you check carat: buyers of flawless stones are choosing much smaller diamonds on average (0.51 vs 1.28 carat). Carat is confounding the clarity-price relationship, a reminder that a single correlation can mislead without checking for a confounding variable underneath it.

## Repository structure

notebooks/diamond_pricing_eda.ipynb holds the full analysis: code, charts, and narrative, in order. data/diamonds_raw.csv is the original, unmodified dataset (53,940 rows). data/diamonds_clean.csv is the version after removing invalid or duplicate rows (53,772 rows). images/ holds exported chart images.

## What's inside the notebook

Phase one is Discover: stating the hypothesis that carat drives price, and the questions being asked before touching the data. Phase two is Structure: inspecting shape, types, and column meanings. Phase three is Clean: finding and removing 168 rows with impossible measurements or exact duplicates. Phase four is Join: not needed here since this is a single-table dataset, noted explicitly rather than skipped. Phase five is Validate: sanity-checking the cleaned data against physical logic, such as the carat vs volume correlation. Phase six is Present: answering the original questions with charts and a written narrative, including the confounding-variable finding above.

## Tools

Python, pandas, seaborn, matplotlib, Jupyter

## Data quality issues found and handled

Twenty rows had physically impossible 0mm measurements. Two rows had measurements around 30mm, likely decimal-point entry errors. There were 146 exact duplicate rows.

## Next step

A multiple regression using carat, cut, clarity, and color together, to isolate each variable's true independent effect. This is covered later in the certificate.

## Source

Dataset: seaborn-data diamonds.csv, github.com/mwaskom/seaborn-data
