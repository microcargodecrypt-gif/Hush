# Hush – Requirements register

Oct 30, 2026

## How to use this register

This register is the single source of truth for what Hush does in MVP1 and what is parked for MVP2. If other documents disagree with it, this register wins.

Each requirement has one status:

- **Delivered (MVP1):** built and working.
- **Delivered (MVP2):** built and working, added after MVP1.
- **Partial (MVP1):** built, with a known gap described in the note.
- **Parked for MVP2:** agreed, deliberately postponed.
- **To decide:** a known gap or idea that has no MVP assigned yet.
- **Dropped:** no longer wanted; kept here so the reason isn't lost.

Whenever a requirement is added, changed, parked or dropped, update this register in the same change and add a line to the change log.

## Summary

Of 35 requirements, 17 were delivered in MVP1 and 2 partly, 2 have been delivered since, 7 are parked for MVP2, and 7 still need a decision.

| Status | Count | IDs |
| --- | --- | --- |
| Delivered (MVP1) | 17 | R-01 to R-05, R-07 to R-16, R-18, R-19 |
| Partial (MVP1) | 2 | R-06, R-17 |
| Delivered (MVP2) | 2 | R-34, R-35 |
| Parked for MVP2 | 7 | R-20 to R-26 |
| To decide | 7 | R-27 to R-33 |
| Dropped | 0 |  |

## Requirements

| ID | Requirement | Area | Status | Decided | Note |
| --- | --- | --- | --- | --- | --- |
| R-01 | Runs fully offline; no data leaves the computer | Platform | Delivered (MVP1) | 30 Oct 2026 | The page blocks all network requests; libraries are bundled inside the file |
| R-02 | Zero install for users: one HTML file opened by double-click | Platform | Delivered (MVP1) | 30 Oct 2026 | Works in Chrome and Edge |
| R-03 | Simple interface | Interface | Delivered (MVP1) | 30 Oct 2026 | Drop zone, results, before/after preview; light and dark mode |
| R-04 | Read Word (.docx), PDF and Excel (.xlsx, .xls) | Files | Delivered (MVP1) | 30 Oct 2026 |  |
| R-05 | Read CSV and plain text | Files | Delivered (MVP1) | 30 Oct 2026 | Added beyond the original ask |
| R-06 | Output in the same format as the input | Files | Partial (MVP1) | 30 Oct 2026 | PDF is rebuilt without its layout; Excel loses cell styling |
| R-07 | Handle \~5,000-row spreadsheets and folders of \~500 documents | Scale | Delivered (MVP1) | 30 Oct 2026 | 5,000 rows processed in about 2 seconds |
| R-08 | English, French and Dutch content | Detection | Delivered (MVP1) | 30 Oct 2026 |  |
| R-09 | Any document containing personal data, with built-in Belgian formats | Scope | Delivered (MVP1) | 30 Oct 2026 |  |
| R-10 | Detect names, emails, phones, national IDs, addresses, account numbers, IP addresses | Detection | Delivered (MVP1) | 30 Oct 2026 | Rule-based; unusual names can be missed |
| R-11 | Financial data: money amounts, IBANs, VAT numbers, cards | Detection | Delivered (MVP1) | 30 Oct 2026 | IDs, IBANs and cards are checksum-validated |
| R-12 | Four levels (Low, Medium, High, Very high) with an editable list per level | Settings | Delivered (MVP1) | 30 Oct 2026 |  |
| R-13 | Quasi-identifiers only at Very high | Settings | Delivered (MVP1) | 30 Oct 2026 | Date of birth, age, gender, nationality, marital status, postal code with city |
| R-14 | Method per data type: removal, masking or pseudonymization | Settings | Delivered (MVP1) | 30 Oct 2026 | Set in CONFIG and changeable per run on screen |
| R-15 | Settings editable by a non-developer | Settings | Delivered (MVP1) | 30 Oct 2026 | Commented CONFIG block at the top of the file |
| R-16 | Quick audit log without original values | Audit | Delivered (MVP1) | 30 Oct 2026 | Shown on screen and exported as CSV |
| R-17 | Apply some regulations | Compliance | Partial (MVP1) | 30 Oct 2026 | GDPR-minded (minimisation, metadata removal); no formal profile |
| R-18 | One-time cleanup: no data is kept between runs | Usage | Delivered (MVP1) | 30 Oct 2026 |  |
| R-19 | Sensible defaults for data utility | Utility | Delivered (MVP1) | 30 Oct 2026 | Chosen by Claude: pseudonymize names and addresses, mask contacts and IBANs, remove IDs |
| R-20 | Consistent pseudonyms across files and runs | Pseudonyms | Parked for MVP2 | 30 Oct 2026 | Today consistent within one file only |
| R-21 | Reversible anonymization with a secure key or lookup table | Pseudonyms | Parked for MVP2 | 30 Oct 2026 |  |
| R-22 | Free-text documents (emails, notes, transcripts) | Scope | Parked for MVP2 | 30 Oct 2026 |  |
| R-23 | Other domains, such as health data | Scope | Parked for MVP2 | 30 Oct 2026 |  |
| R-24 | Formal guarantees such as k-anonymity | Compliance | Parked for MVP2 | 30 Oct 2026 |  |
| R-25 | Compliance profiles (e.g. GDPR presets) | Compliance | Parked for MVP2 | 30 Oct 2026 |  |
| R-26 | Advanced audit trail | Audit | Parked for MVP2 | 30 Oct 2026 | E.g. run ID, settings snapshot, file hashes, tamper-evident log |
| R-27 | OCR for scanned PDFs | Files | To decide |  | Scanned PDFs are skipped today |
| R-28 | Keep the original PDF layout | Files | To decide |  |  |
| R-29 | Keep Excel cell styling | Files | To decide |  |  |
| R-30 | Support legacy .doc files | Files | To decide |  | Workaround: save as .docx first |
| R-31 | Review step to accept or reject each detection before export | Interface | To decide |  | Idea raised by Claude |
| R-32 | "Always" and "never" anonymize word lists (for example organisation or project names) | Settings | To decide |  | Idea raised by Claude |
| R-33 | Realistic fake values as a fourth method | Pseudonyms | To decide |  | Idea raised by Claude |
| R-34 | Short guided tour on first visit | Interface | Delivered (MVP2) | 22 Nov 2026 | Four steps: add a file, choose a level, check what gets hidden, anonymize. Skip at any time; replay with "Show me around". Remembered in the browser |
| R-35 | "What gets anonymized" list appears after a file is added, with counts | Interface | Delivered (MVP2) | 22 Nov 2026 | A quick scan shows how often each type was found; types not found are greyed out but stay usable. 5,000 rows scanned in under half a second |

## Change log

| Date | Change |
| --- | --- |
| 30 Oct 2026 | Register created: 17 delivered, 2 partial, 7 parked for MVP2, 7 to decide. This version is the MVP1 snapshot. |
| 22 Nov 2026 | Reworded as a general-purpose tool ahead of open-sourcing. No requirement changed. |
| 22 Nov 2026 | Added R-34 (guided tour) and R-35 (data list after upload, with counts), both delivered. New status: Delivered (MVP2). |
