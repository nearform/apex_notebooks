# Inconsistencies in COA
As we've reviewed the Chart of Accounts (COA), we've identified several inconsistencies - such as missing classifications, account code formatting irregularities, and duplicate account names with differing attributes.

Our understanding is that the COA is the system for recording fund transactions are mapped into. In it's current form the COA presents some challenges for mapping and transformation. We want to align expectations before we proceed further.

Could you please clarify the following:

- Are the inconsistencies in the COA intentional as part of evaluating how imperfect data will be handled as part of the POC?
- Would you prefer we correct and normalize the COA for the sake of the POC?
- Alternatively, should we use the COA as is and flag records that cannot be mapped cleanly?



## Inconsistency details

###  Duplicate Account Name with Different Attributes (Total: 70)
Examples:
- Account Name: Expense Accrual, Account Code: 24-00, Trial Balance Class: Liabilities, Type: Other, **Financial Statement Class: -**
- Account Name: Expense Accrual, Account Code: 240111, Trial Balance Class: Liabilities, Type: Other, **Financial Statement Class: Accounts Payable and Accrued Expenses**
---------------------------------------
- Account Name: Capital, Account Code: 39\zz, **Trial Balance Class: -**, Type: Other, Financial Statement Class: -
- Account Name: Capital, Account Code: 3-00, **Tria Balance Class: Equity**,Type: Other, Financial Statement Class: -


### Inconsistency name: Account Code with Invalid Format (Total: 29)
Examples:
- Account Code: 199999\zz, Account Name: Assets, Trial Balance Class: -, Type: Other, **Financial Statement Class: -**
- Account Code: 149\zz, Account Name: Prepaid Expenses, **Trial Balance Class: -**, Type: Other, **Financial Statement Class:** -
- Account Code: 530999\zz, Account Name: Property Charges, **Trial Balance Class: -**, Type: Other, **Financial Statement Class: -**


### Inconsistency name: Rows with Missing Critical Fields (Total: 67)
Examples:
- Account Code: 18-00, Account Name: Miscellaneous, Trial Balance Class: Assets, Type: Other, **Financial Statement Class: -**
- Account Code: 15-00, Account Name: Income Accrual, Trial Balance Class: Assets, Type: Other, **Financial Statement Class: -**
- Account Code: 650111, Account Name: Unfunded Commitment Receivable, Trial Balance Class: Other, Type: Other, **Financial Statement Class: -**
