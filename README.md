# Personal Finance — PWA

A private, offline-capable personal finance planner designed for iPhone and GitHub Pages. No account, backend, analytics, or third-party libraries are required.

## Features
- Dashboard with monthly metrics, savings chart, category breakdown and quick actions.
- Month-specific salary settings and payslip calculation. New months start with zero salary settings; use Reset month to defaults and then Save salary settings to activate saved defaults. Paid days default to 18.5 when no leave overlaps the month, otherwise actual Thu–Sun workdays are counted outside leave dates.
- Leave planner that counts actual Thursdays, Fridays, Saturdays and Sundays in each month, excluding leave dates.
- USD and MVR expense entries, with a monthly editable exchange rate; copy the previous month’s expenses and edit or delete individual entries.
- Other income tracking for side jobs, freelance work, gifts and any income outside salary.
- Savings goals with USD or MVR targets, monthly/yearly/within-next-months durations, and contribution progress.
- Dedicated debts and loans tracker with editable records, editable/deletable payment history, historical month-end balances, and separate Active and Completed views.
- Annual report and CSV export.
- JSON backup and restore.
- Local browser storage and offline PWA cache.

## Savings and allocations
USD savings are calculated from net salary and USD income after USD expenses and the USD amount needed for uncovered MVR expenses. MVR income and MVR debt collections can cover MVR expenses; unused amounts remain in a separate MVR savings balance. MVR savings can be applied to later MVR expenses to reduce the USD exchange required. USD and MVR balances carry forward across years, with opening balances for 2026 set to zero.

## Salary calculation
Gross = base salary + (daily allowance × paid working days) + telephone allowance + other allowances.
Net = gross − (base salary × pension percentage) − social fund. A month with salary settings not yet saved has a zero salary calculation.

## Debts & loans
- Debt and loan records are stored in a shared device-level ledger so they remain visible when switching budget years. The selected month filters balances and payment history through that month end; later-dated payments remain saved but are not included in earlier months.
- Fully paid records can be signed off into a separate Completed view; records and payment history are retained.
- Edit or delete debt records and individual payment transactions; balances recalculate from the transaction history.
- **I borrowed (I owe):** money you need to repay to another person or lender.
- **Someone borrowed from me (they owe me):** money another person needs to repay to you.
- Add the original amount, currency, person, date, optional due date and notes.
- Use **Record payment** to add dated repayments or collections and update the outstanding balance. USD repayments become USD expenses; USD collections become additional USD income. MVR repayments become MVR expenses; MVR collections ask how much to use against MVR expenses, with the remainder saved in MVR.

## Supported budget years
The year selector supports 2026 through 2036. Each year has its own monthly budget records, while USD and MVR savings balances carry forward on the same device.

## Publish free with GitHub Pages
1. Create a GitHub repository (for example, `personal-finance`).
2. Upload **all files inside this folder** to the repository root: `index.html`, `styles.css`, `app.js`, `manifest.webmanifest`, `sw.js`, `icon.svg`, and `README.md`.
3. Open repository **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**; choose `main` and `/ (root)`, then Save.
5. Wait for GitHub Pages to publish. Your app address will look like `https://YOUR-USERNAME.github.io/personal-finance/`.

## Install on iPhone
1. Open the published address in Safari.
2. Tap Share → Add to Home Screen.
3. Enable “Open as Web App” if shown, then tap Add.

## Data and backups
- Finance records are stored in this browser's local storage on the device. They are not uploaded to GitHub.
- Existing Ameer Finance browser records are retained because the app keeps the original local-storage keys.
- Export a JSON backup regularly, especially before clearing Safari website data, changing browsers, or changing phones.
- To move records to another device, export the backup on the old device and import it on the new device.
- A public repository makes the source code visible; never put personal finance records or backup files in the repository.
- This is a budgeting tool, not a payroll system. Confirm payslips against your employer's actual payroll calculation.


## Additional income in USD or MVR
- Record other income in either USD or MVR.
- USD income is added to the USD savings calculation.
- For MVR income, enter the amount (if any) to use against the selected month's recorded MVR expenses. Leave this at 0 to save all of the MVR income.
- Any MVR income not allocated to expenses is recorded as MVR savings, with a monthly and running MVR savings ledger.
- MVR allocated to expenses reduces the remaining MVR expense amount used to calculate how much USD must be exchanged.
- Existing MVR income entries without an allocation are treated as fully saved in MVR.

Update note: the service-worker cache is version 7. After deploying, close and reopen the PWA or refresh Safari if the old interface remains cached.


## Year-to-year savings
- 2026 starts with USD 0.00 and MVR 0.00 opening balances.
- Closing USD and MVR savings balances are carried into the following year automatically on this device.
- Keep using the same browser/device storage or transfer the relevant backups when moving devices.
- The app stores yearly records separately; do not clear website data without exporting backups.
