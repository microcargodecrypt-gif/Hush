<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/hush-logo-dark.svg">
    <img src="assets/hush-logo.svg" alt="Hush" width="320">
  </picture>
</p>

<p align="center"><strong>Anonymize documents on your own computer before they go into AI.</strong><br>
Private by design · Runs in your browser and offline · Word, PDF, Excel · English, French, Dutch</p>

<p align="center"><a href="https://microcargodecrypt-gif.github.io/Hush/"><strong>▶ Try it in your browser</strong></a></p>

# Hush

Remove personal data from your documents **on your own computer**, before you upload them to an AI tool.

Hush is a single HTML file. You open it in Chrome or Edge, drop your files, pick a level and download anonymized copies. Nothing is installed and nothing is sent anywhere: the page blocks every network request.

> **Status: MVP 1.** Detection is rule-based. Always review the output before you share it.

## Why

More and more people ask AI assistants about their own documents, and those documents often contain personal data: names, addresses, phone numbers, ID or bank account numbers. Hush strips or replaces that data first, whatever the document is, so only the anonymized version leaves your machine.

Detection works in **English, French and Dutch**, with built-in support for Belgian formats (national register numbers, VAT numbers, cities and common first names). Most rules, such as emails, phone numbers, IBANs and card numbers, work for documents from other countries too, and the word lists can be extended.

## Quick start

1. Download [`Hush.html`](Hush.html) (on GitHub: open the file, then click **Download raw file**).
2. Double-click it. It opens in your browser. Chrome and Edge are supported.
3. Choose a level, drop files or a whole folder, and click **Anonymize files**.
4. Check the before/after preview, then download the files (one by one or as a .zip) and the audit log.

You can also [try it in your browser](https://microcargodecrypt-gif.github.io/Hush/) without downloading anything. It runs the same way: the files you drop are processed in your browser and are not uploaded.

## Try it with sample documents

Don't want to use your own files for a first try? The [`samples`](samples/) folder holds six made-up documents in English, French and Dutch: two Word files, two PDFs, an Excel list and a CSV. Everything in them is invented, but the ID, IBAN and VAT numbers pass the same checks as real ones.

1. Download [all samples as a .zip](https://microcargodecrypt-gif.github.io/Hush/samples/hush-samples.zip) and unzip it.
2. Open Hush, choose **Very high** and drop the files on the page.
3. Click **Anonymize files** and compare the before and after preview.

The [samples page](samples/README.md) lists what each file contains.

## What it does

| | |
| --- | --- |
| **Files** | Word (.docx), PDF, Excel (.xlsx, .xls), CSV and plain text |
| **Output** | Same format as the input. Word keeps its formatting and loses author metadata. Excel loses cell styling. PDFs are rebuilt as text PDFs without the original layout. |
| **Scale** | Spreadsheets of about 5,000 rows (about 2 seconds) and folders of several hundred documents |
| **Audit log** | CSV of file, location, data type and method. It never contains the original values. |

### Levels

| Level | Anonymizes |
| --- | --- |
| Low | Person names and street addresses |
| Medium | adds email addresses, phone numbers and social media profile links |
| High | adds national ID numbers, IBANs, credit cards, VAT numbers, IP addresses and money amounts |
| Very high | adds quasi-identifiers: date and place of birth, age, gender, nationality, marital status, postal code with city |

### Methods

Each data type can be handled in one of three ways, by default or per run on screen:

- **Remove:** `[REMOVED]`
- **Mask:** `s***@g***.com`
- **Pseudonymize:** `[PERSON_1]`, consistent for the same person within one file

National IDs, IBANs and card numbers are checksum-validated to avoid false positives.

## How your data stays local

- Everything runs as JavaScript inside the page. There is no server.
- A Content Security Policy at the top of the file (`default-src 'none'`) stops the page from loading or sending anything over the network.
- All libraries are bundled inside the file, so it also works with no internet connection.

You can check this yourself: open your browser's developer tools, go to the **Network** tab, and anonymize a file. No request leaves the page.

## Configuration

All settings live in a commented `CONFIG` block at the top of `Hush.html`. Open the file in any text editor, change a list, save and reload. You can change:

- which data types each level covers, and the default method for each type
- spreadsheet column names that mark a whole column as a data type
- labels such as "Name:" or "Date of birth:" that introduce a value in documents
- first names, stopwords and Belgian cities used by name and address detection

See [docs/configuration.md](docs/configuration.md).

## Known limits

- Detection is rule-based. Unusual names can be missed, and company addresses are anonymized too.
- Scanned PDFs have no text layer and are skipped (no OCR yet).
- Old `.doc` files must be saved as `.docx` first.
- Pseudonyms are consistent within one file, not across files or runs.
- The tool is not reversible: there is no key to restore the original values.

The full list of what is delivered, parked and still open is in the [requirements register](docs/requirements-register.md).

## Try it in your browser

Hush is available online at **https://microcargodecrypt-gif.github.io/Hush/**. The page is the same file as the download and is still blocked from sending data: your files are read by your browser and never uploaded.

## Contributing

Bug reports, missed detections and pull requests are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) first, and **never attach real personal data** to an issue: use made-up examples.

To report a privacy or security problem, see [SECURITY.md](SECURITY.md).

## Licence

Hush is released under the [Apache License 2.0](LICENSE). See also [NOTICE](NOTICE).

It bundles these open-source libraries, each under its own licence. Details are in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

| Library | Version | Licence |
| --- | --- | --- |
| SheetJS Community Edition | 0.18.5 | Apache-2.0 |
| PDF.js (Mozilla) | 3.11.174 | Apache-2.0 |
| jsPDF | 2.5.1 | MIT |
| JSZip (with pako) | 3.10.1 | MIT (chosen from MIT or GPLv3) |

## Disclaimer

This tool reduces the personal data in a document. It does not guarantee anonymity in the legal sense, and it does not make a use of personal data compliant with the GDPR or any other law by itself. You remain responsible for checking the output and for how you use it.
