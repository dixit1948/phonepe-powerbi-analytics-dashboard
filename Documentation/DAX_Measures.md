# DAX Measures
> ⚠️ Reference templates. Replace table/column names with those in **your** PBIX and paste your exact formulas.

```DAX
Total Transactions = COUNTROWS(Transactions)

Total Value = SUM(Transactions[Amount])

Unique Users = DISTINCTCOUNT(Transactions[UserID])

Successful Rate =
DIVIDE(
    CALCULATE(COUNTROWS(Transactions), Transactions[Status] = "Successful"),
    COUNTROWS(Transactions)
)

Transactions PM =
CALCULATE([Total Transactions], DATEADD('Date'[Date], -1, MONTH))

MoM Growth % =
DIVIDE([Total Transactions] - [Transactions PM], [Transactions PM])

Transactions PY =
CALCULATE([Total Transactions], SAMEPERIODLASTYEAR('Date'[Date]))

YoY Growth % =
DIVIDE([Total Transactions] - [Transactions PY], [Transactions PY])
```
