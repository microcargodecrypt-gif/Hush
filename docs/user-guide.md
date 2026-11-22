# User guide

## What it is

Hush removes personal data from documents on your own computer before you upload them to an AI tool for analysis. It is a single HTML file (`Hush.html`, about 2.7 MB) that runs fully offline in Chrome or Edge. Nothing needs to be installed, and the page is technically blocked from contacting the internet.

It works on any document that contains personal data, such as letters, reports, forms, spreadsheets or exported lists. Detection works in English, French and Dutch, with built-in support for Belgian formats such as national register numbers and city names.

It is a one-time cleanup tool: drop files or a folder, pick a level, click **Anonymize files**, then download the files with an audit log.

## Step by step

1. Open `Hush.html` in Chrome or Edge (double-click it).
2. Pick an **anonymization level**. The level sets which data types are ticked.
3. Optionally tick data types on or off, and choose for each one whether to **remove**, **mask** or **pseudonymize** it.
4. Drop files or a whole folder on the drop zone, or use **Choose files** / **Choose a folder**.
5. Click **Anonymize files**.
6. Check the **Before and after** preview.
7. Download each file, or **Download all (.zip)**, and **Download audit log (.csv)**.

## Supported files

| Type | Read | Written back as |
| --- | --- | --- |
| Word (.docx) | Yes | .docx, formatting kept, author metadata removed |
| PDF | Yes, if it has a text layer | text PDF, original layout not kept |
| Excel (.xlsx, .xls) | Yes | spreadsheet, cell styling not kept |
| CSV, plain text | Yes | same format |
| Old Word (.doc) | No | Save as .docx in Word first |
| Scanned PDF | No | Needs OCR, not included yet |

Volumes of about 5,000 spreadsheet rows or about 500 documents in a folder are expected to work.

## Levels

- **Low:** names and street addresses.
- **Medium:** adds email addresses, phone numbers and social media profile links.
- **High:** adds national ID numbers, IBANs, credit cards, VAT numbers, IP addresses and money amounts.
- **Very high:** adds quasi-identifiers (date and place of birth, age, gender, nationality, marital status, postal code with city).

## Methods

- **Remove:** the value is deleted and replaced by `[REMOVED]`. In Excel and CSV the cell is emptied.
- **Mask:** most of the value is hidden, for example `s***@g***.com`.
- **Pseudonymize:** the value is replaced by a label such as `[PERSON_1]`. The same person gets the same label throughout one file.

Default methods: names and addresses are pseudonymized, emails, phones and IBANs are masked, IDs and quasi-identifiers are removed.

## Audit log

The audit log is a CSV that records, for each replacement, the file, the location, the data type and the method. It never contains the original values, so it is safe to keep next to the anonymized files.

## Known limits

- Detection is rule-based, so unusual names can be missed, and company addresses are anonymized too.
- Scanned PDFs are skipped.
- Pseudonyms are not consistent across files or runs, and anonymization cannot be reversed.
- Always review the output before sharing it.
