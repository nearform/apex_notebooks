# Data Validation Checks – Results

**File:** `findings_data_consolidation_01.md`  
**Data Extracted:** 2024-07-01

=== Starting Data Validation Checks ===

## 1. Checking investors_df

Investor Region value counts:
Investor Region
???    4603
Name: count, dtype: int64  
Why: Ensure region data is populated and consistent for schema design and reporting.

Investor Legal Name different from Investor ID: 0 rows  
Why: Identify if legal name is meaningful or just duplicated from ID, possibbly impacting schema design.

Missing Investor First Name: 3,874, 84.16%  
Missing Investor Last Name: 3,874, 84.16%  
Why: Identifies if legal name is meaningful.

Duplicate Investor IDs: 13  
Why: Ensures primary key uniqueness for migration integrity.

---

## 2. Checking investors_accounts_df

Duplicate Investor Account IDs: 0  
Why: Ensure primary key uniqueness for migration integrigy.

Accounts with invalid Fund IDs: 0  
Why: Validates referential integrity between accounts and funds.

Missing Investor for Account: 135, 2.07%  
Why: Highlights potential orphaned records.

---

## 3. Checking managed_funds_df

Fund Legal Name different from Fund ID: 0 rows  
Why: Identify if legal name is meaningful or just duplicated from ID, possibly impacting schema design.

Funds with date inconsistencies: 10  
Why: Ensures date fields are logically consistent for reporting and analysis.

Duplicate Fund IDs: 0  
Why: Ensures primary key uniqueness for migration integrity.

Null Fund IDs: 0  
Why: Ensures all funds have valid identifiers for referential integrity.

Unrealistic Fund Start Dates: 0  
Why: Ensure start dates are valid and consistent with accounting records.

---

## 4. Checking transactions_with_details_df

Invalid Entry Dates: 0  
Why: Ensures date parsing is correct for reporting and analysis.

Transactions with Fund names not in managed_funds_df: 2,424  
Why: Validates referential integrity between transactions and managed funds.

Negative debit rows: 55, Negative credit rows: 14  
Why: Identifies potential data entry errors or anomalies in transaction amounts.

Zero debit rows: 204,695, Zero credit rows: 184,863  
Why: Identifies incomplete or placeholder entries.

Non-null counts in 'Unnamed' columns:  
Unnamed: 25    0  
Unnamed: 26    4  
dtype: int64  
Why: Identifies unintended data leakage into placeholder columns.

---

## 5. Checking fund_ops_df

Fund for Account missing: 5,654,180, 98.04%  
Why: Identify missing associations between funds and accounts, which can impact reporting and analysis.

Investor for Account missing: 113,035, 1.96%  
Why: Identify potential orphaned records.

Fund Op Date range: 2010-11-23 00:00:00 to 2025-03-31 00:00:00  
Why: Ensures date range is logical and consistent with fund operations.

Negative Fund Currency Amount rows: 3,240,988  
Negative Fund Currency Amounts by Component Type:  
Component Type
Unrealized Gain- Investment MTM              761440  
Other Expense                                711074  
Tax Prep Fees                                209942  
Administrative Fees                          180065  
Audit Fees                                   151460  
...  
Transfer - Carried Interest                       1  
Transfer - Distribution                           1  
Deemed Capital Call for Management Fees R         1  
Holdback: Management Fees Offset                  1  
Tax Withholdings – Fund as Corp                   1  
Name: count, Length: 122, dtype: int64  
Why: Identifies potential data entry errors or anomalies in fund operations.

---

## 6. Cross-table referential integrity checks

Accounts with invalid Investor IDs: 6,529  
Why: Validates all accounts are linked to valid investors.

Fund Ops with invalid Investor Accounts: 0  
Why: Ensures fund operations are linked to valid investor accounts for relational schema integrity.

---

## 7. Coverage proportion checks

Proportion of investor accounts linked to existing investors: 0.00%  
Why: Indicates the completeness of investor-account relationships.

Proportion of fund ops linked to existing investor accounts: 100.00%  
Why: Indicates the completeness of fund operations linked to investor accounts.

---

## 8. Fully duplicated rows checks

Fully duplicated rows in investors_df: 0  
Fully duplicated rows in investors_accounts_df: 0  
Fully duplicated rows in managed_funds_df: 0  
Fully duplicated rows in transactions_with_details_df: 0  
Fully duplicated rows in fund_ops_df: 738,321, out of: 5,767,213)  
Why: Identifies potential data entry errors or redundant records that may affect analysis and reporting.

=== Data Validation Checks Complete ===
