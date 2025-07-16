# Derived values in the Chart of Accounts
The following values in the Chart of Accounts (COA) are typically derived, i.e. calculated value, that do not appear in the sample data provided.

| Account Name                 | Reason It’s Derived                                                |
| ---------------------------- | ------------------------------------------------------------------ |
| **Accumulated Depreciation** | Calculated over time from depreciation schedules                   |
| **Realised FX Reserve**      | Requires tracking currency exchange impacts on closed transactions |
| **Unrealised FX Reserve**    | Tracks currency gains/losses on open positions                     |
| **Depreciation Expense**     | Periodic write-off of asset value                                  |
| **Depreciation**             | May be a duplicate or alternative label for the above              |

# Assumptions
For the current POC scope:

- These accounts are not covered by the sample data.
- They can be excluded them from initial loading and mapping.
