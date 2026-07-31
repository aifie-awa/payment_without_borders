# China Bank / CNAPS Reference Data — Data Dictionary

Reference data mapping supported bank branches in China to their **CNAPS code** and **postal code**. It powers the guided "Send to China" flow (pick Bank → Province → City → Branch; CNAPS and postal code resolve automatically).

## Files

| File | Rows | Description |
|---|---|---|
| `china-banks-selected.csv` | ~74,029 | **Selected (major) banks** — 15 banks incl. ICBC, CCB, ABC, Bank of China, Bank of Communications, China Merchants Bank, Postal Savings Bank, CITIC, etc. |
| `china-banks-other.csv` | ~74,679 | **Other banks** — 112 banks incl. rural credit cooperatives, rural/city commercial banks, village & township banks, policy banks. |
| `curated-banks.json` | 802 branches | **Prototype subset** — nested `bank → province → city → [branch]` used by the interactive demo. A real slice (8 banks · 6 provinces) with genuine CNAPS codes. |

Combined: **~148,700 branch records · 127 banks · 31 provinces · 336 cities.**

## Columns (both CSVs)

| Column | Type | Description | Example |
|---|---|---|---|
| `Bank` | string | Bank name. Top-level dropdown value. | `Industrial and Commercial Bank of China` |
| `Province` | string | Province the branch sits in. Second dropdown. | `Zhejiang` |
| `City` | string | City / county. Third dropdown. | `Zhoushan City` |
| `Branch Name` | string | Specific branch. Fourth dropdown. | `ICBC Limited Zhoushan Chengdong Branch` |
| `CNAPS Code` | string (12 digits) | China National Advanced Payment System code that routes an RMB payment to this exact branch. **Auto-resolved on branch selection.** | `102342002074` |
| `Postal Code` | string (6 digits) | Branch postal code. Auto-resolved. | `310000` |

## `curated-banks.json` shape

```json
{
  "Industrial and Commercial Bank of China": {
    "Zhejiang": {
      "Zhoushan City": [
        { "branch": "ICBC ... Zhoushan Chengdong Branch", "cnaps": "102342002074", "postal": "310000" }
      ]
    }
  }
}
```

## Notes & caveats

- **CNAPS codes are the unique routing key.** Branch names can be similar across locations; the CNAPS code disambiguates.
- **Postal codes** may be city- or province-level where a precise branch value wasn't available in the source (the original workbook flagged match confidence). Treat as best-available.
- Some rows describe internal/management units marked *"not handling external business"* — these are excluded from the prototype and should be filtered out of any customer-facing dropdown.
- Bank/branch names occasionally include the source language phrasing; normalise for display as needed.
- Source: consolidated from the `China Bank_CNAPS_Postal Codes.xlsx` workbook (sheets *Selected Banks* and *Other Banks*).

## Using it in an app

Build a nested lookup keyed `Bank → Province → City → Branch`. Populate each dropdown from the distinct values at that level filtered by the selections above it; on branch selection, read `CNAPS Code` and `Postal Code` and attach them to the transfer payload. Never submit a transfer without a resolved CNAPS code.
