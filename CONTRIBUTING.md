# Contributing

Thanks for helping. Hush is a small project, so a short issue or a focused pull request goes a long way.

## The one rule: no real personal data

Never paste, attach or commit real documents or anything that identifies a real person, even "just for testing". Use made-up names, addresses and numbers. For IBANs or national register numbers, use well-known test values or generate fictional ones that pass the checksum.

If you accidentally post real data in an issue, edit or delete it straight away.

## Reporting a missed or wrong detection

Use the **Missed or wrong detection** issue template. The most useful report gives:

- a short, made-up snippet that reproduces the problem
- the file type (Word, PDF, Excel, CSV, text) and language (EN, FR, NL)
- the level and method you used
- what you expected and what happened

## Suggesting a feature

Check the [requirements register](docs/requirements-register.md) first: many ideas are already listed as parked or to decide. Then open a **Feature request**.

## Making changes

The whole tool is one file, `Hush.html`:

- The `CONFIG` block at the top holds all settings and word lists. Many improvements (a new first name, a column header, a city) only need a change there.
- The anonymization engine (detection and replacement) is in its own `<script>` block, separate from the user interface code.
- The bundled libraries sit in their own `<script>` blocks. Don't edit them; upgrade them as a whole and update [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

Rules for changes:

1. **Keep it offline.** No change may add a network request, an external script, a font from a CDN or analytics. The Content Security Policy at the top must stay as strict as it is.
2. **Keep it a single file** that works by double-click in Chrome and Edge.
3. **Test by hand** with fictional files in each format you touched, at each level you touched, and check the before/after preview and the audit log.
4. **Update the docs.** If a requirement is added, changed, parked or dropped, update [docs/requirements-register.md](docs/requirements-register.md) and add a line to its change log.

## Pull requests

- One topic per pull request.
- Describe what changed and how you tested it.
- By submitting a pull request you agree that your contribution is released under the project's [Apache License 2.0](LICENSE).
