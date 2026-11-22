# Configuration

All settings are in the `CONFIG` block at the top of `Hush.html`. You don't need to be a developer to change them.

1. Open `Hush.html` in a text editor (Notepad, TextEdit in plain-text mode, VS Code).
2. Change a value or a list in the `CONFIG` block. The comments in the file explain each part.
3. Save, then reload the page in your browser.

Rules of thumb: text goes between quotes (`"like this"`), list items are separated by commas (`["a", "b", "c"]`), and the commas at the end of lines must stay.

## What you can change

| Setting | What it does |
| --- | --- |
| `defaultLevel` | Level selected when the page opens: `"low"`, `"medium"`, `"high"` or `"very_high"` |
| `levels` | Which data types each level anonymizes |
| `levelInfo` | Label and description shown for each level |
| `entities` | For each data type: its label, default `method` (`"removal"`, `"masking"` or `"pseudonymization"`), the `token` used in pseudonyms, and whether it is a quasi-identifier |
| `removalText` | What removal leaves behind in Word, PDF and text files (default `[REMOVED]`) |
| `clearCellsOnRemoval` | In Excel and CSV, empty the cell instead of writing the removal text |
| `maskChar` | Character used for masking (default `*`) |
| `stripDocumentMetadata` | Remove author and "last modified by" from Word files |
| `firstLineIsNameInProfiles` | In résumé-style documents (with headings such as Experience or Education), treat the first line as the person's name |
| `columnHints` | Words in a spreadsheet column header that mark the whole column as a data type |
| `columnExclusions` | Header words that stop a column from being treated as names, addresses or cities (for example "Organisation") |
| `labels` | Words that introduce a value in documents, such as "Name:", "Nom :" or "Geboortedatum:" |
| `firstNames` | Common first names that help recognise person names |
| `nameStopwords` | Words that are never part of a name (headings, months, job words) |
| `belgianCities` | Belgian cities and municipalities, used to recognise "2000 Antwerpen" |

## Examples

Make **High** the default level:

```js
defaultLevel: "high",
```

Pseudonymize emails instead of masking them:

```js
email: { label: "Email addresses", method: "pseudonymization", token: "EMAIL" },
```

Treat a column headed "Deelnemer" (participant) as person names: add `"deelnemer"` to `columnHints.person_name`.
