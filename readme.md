# Consumer Credit Risk Analysis

A descriptive analysis of how credit limits and repayment histories
relate to default rates in the following month among 30,000 credit
card clients.

## Project objective

Compare observed default rates across borrower groups and identify
patterns that could inform further investigation of credit risk.

This project uses Python, pandas, and Matplotlib. It does not build
a predictive model or estimate the effects of lending interventions.

## Data

Source: UCI Machine Learning Repository, Default of Credit Card Clients.

The dataset covers 30,000 credit card clients in Taiwan, with repayment
history from April to September 2005. Monetary values are expressed
in New Taiwan dollars (NT$).

The outcome records default payment in the following month, coded
1 for default and 0 otherwise.

The original Excel file is used without manual changes. Data preparation
is performed in the notebook.

## Analysis

1. Check missing values, duplicate records, client IDs, and outcome codes.
2. Calculate the overall default rate.
3. Compare default rates by September repayment status.
4. Compare default rates across credit limit bands.
5. Count months with positive repayment delay codes and compare outcomes.
6. Compare September repayment status groups within credit limit bands.

Group sizes are reported alongside default rates to support interpretation.

## Key findings

Overall, 6,636 of 30,000 clients defaulted, giving a default rate of 22.12%.

The default rate was 31.79% for clients with credit limits up to
NT$50,000, compared with 13.26% for limits above NT$300,000.

Clients with no positive monthly delay codes had an observed default
rate of 11.71%, compared with 70.32% for clients with positive delay
codes in all six months.

Among clients with a September delay code of two months or more,
default rates ranged from 68.10% to 71.35% across credit limit bands.

Repayment delays were associated with high default rates even within
higher credit limit bands. A higher credit limit alone therefore did
not identify a group with low default rates among these delayed accounts.

These patterns could motivate further investigation of monitoring
based on repayment history. They do not establish that a particular
lending or collection policy would improve outcomes.

## Limitations

The sample concerns Taiwan in 2005. Findings may not generalise to
current borrowers or other countries.

Repayment codes negative two and zero are not defined in the supplied
documentation. They are retained as separate categories without
assuming their meaning.

Having no positive delay codes does not establish that every payment
was made on time.

The number of months with positive delay codes measures monthly records,
not necessarily separate episodes of delinquency.

Credit limit bands are analytical choices. Alternative boundaries
could produce different comparisons.

Default rates for smaller groups are less precise.

The analysis is descriptive and does not establish causation,
predictive performance, or expected monetary losses.

## Files

1. `credit_risk_analysis.ipynb`: analysis, tables, charts, and interpretation.
2. `default of credit card clients.xls`: source dataset. Obtain from UCI
   if it is not included in this repository.
3. `requirements.txt`: Python dependencies.
4. `.gitignore`: files and directories excluded from version control.

## How to run

1. Download or clone this repository.
2. Obtain the source Excel file from UCI and place it beside the notebook.
   Keep the filename `default of credit card clients.xls`.
3. Create or activate a Python environment.
4. Install the dependencies using the following terminal command:

       python -m pip install -r requirements.txt

5. Open `credit_risk_analysis.ipynb` in VS Code with the Python and
   Jupyter extensions installed.
6. Select that Python environment as the notebook kernel.
7. Run all cells from top to bottom.

## Possible extensions

1. Check whether findings are sensitive to credit limit band boundaries.
2. Quantify uncertainty around group default rates.
3. Develop and evaluate a baseline predictive model on a separate test set.
4. Compare potential monitoring rules by coverage, default capture,
   and the number of clients flagged who did not default.