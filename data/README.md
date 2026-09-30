# Course dataset: Default of Credit Card Clients (Taiwan, 2005)

**Source.** UCI Machine Learning Repository, dataset #350.
Download: https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients
Original paper: Yeh, I-C. & Lien, C-H. (2009). "The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients." *Expert Systems with Applications*, 36(2), 2473–2480.

**File.** `raw/default of credit card clients.xls` (Excel 97–2003; needs the `xlrd` package). Never edit this file: all cleaning happens in code.

**Unit of observation.** One credit card holder at a Taiwanese bank. 30,000 clients, observed April–September 2005. Amounts are in New Taiwan dollars (NT$).

## Codebook (as documented by the source)

| Column | Meaning |
|---|---|
| `ID` | Client identifier |
| `LIMIT_BAL` | Credit limit granted (individual + family/supplementary), NT$ |
| `SEX` | 1 = male, 2 = female |
| `EDUCATION` | 1 = graduate school, 2 = university, 3 = high school, 4 = others |
| `MARRIAGE` | 1 = married, 2 = single, 3 = others |
| `AGE` | Age in years |
| `PAY_0`, `PAY_2` … `PAY_6` | Repayment status in Sep, Aug, Jul, Jun, May, Apr 2005. −1 = paid duly; 1 = one month late; 2 = two months late; … 9 = nine or more months late |
| `BILL_AMT1` … `BILL_AMT6` | Bill statement amount, Sep → Apr 2005, NT$ |
| `PAY_AMT1` … `PAY_AMT6` | Amount paid, Sep → Apr 2005, NT$ |
| `default payment next month` | 1 = client defaulted (October 2005), 0 = did not |

## Known traps (discovered in Session 1, handled in Session 2)

- The real header is on the **second** row of the sheet (`header=1`).
- There is no `PAY_1`: the sequence is `PAY_0, PAY_2, …, PAY_6`.
- `EDUCATION` takes values 0, 5, 6 and `MARRIAGE` takes 0: none are documented.
- `PAY_*` takes values −2 and 0, which are not documented either.
- 590 clients have a negative September bill (`BILL_AMT1 < 0`).
- 35 rows are identical on every column except `ID`.
- All columns load as `int64`, including categorical ones (`SEX`, `EDUCATION`, `MARRIAGE`).

## The three research questions

1. **RQ1: Education and default.** Do default rates differ across education levels? *(Session 3: chi-square test)*
2. **RQ2: Credit limits.** Do clients who default have lower credit limits than those who do not? *(Session 3: t-test / Mann–Whitney)*
3. **RQ3: Repayment history.** Does recent repayment behaviour predict default, beyond the credit limit and demographics? *(Session 3: linear regression)*
