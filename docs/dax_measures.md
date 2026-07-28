DAX Measures
Default Rate %
dax
Default Rate % = DIVIDE(CALCULATE(COUNTROWS(Loans), Loans[loan_status]=1), COUNTROWS(Loans))

Percentage of loans in the current filter context that have defaulted. Uses DIVIDE instead of / to avoid divide-by-zero errors when a filtered view has no rows.

Avg Interest Rate
dax
Avg Interest Rate = AVERAGE(Loans[loan_int_rate])

Average interest rate across loans in the current filter context. Since nulls in loan_int_rate were already imputed with grade-level medians during data cleaning (see main README), this simple average is reliable without additional null handling.

Total Loans (via Card visual)

Count of loan_status (or any non-null column), aggregation set to Count — total number of loan records in the current filter context.

Total Loan Amount (via Card visual)

Sum of loan_amnt — total dollar value of loans in the current filter context.

Total Defaulted Loans (Default Analysis page)

Count of loan_status, with the page-level filter loan_status = 1 applied — total number of defaulted loans in the current filter context.

Content
