# Security and privacy issues

Hush exists to keep personal data on your computer. Two kinds of problem are treated as security issues:

- anything that could make the page send data over the network, or weaken its Content Security Policy
- a systematic failure that leaves a whole category of personal data in the output (for example, every IBAN in a given format)

## How to report

Please **don't open a public issue** for these. Use GitHub's private reporting instead: go to the **Security** tab of this repository and click **Report a vulnerability**.

Do not include real personal data in the report. A made-up example that reproduces the problem is enough.

## Ordinary missed detections

A single unusual name or address that is not caught is a normal limit of rule-based detection, not a security issue. Report it with the **Missed or wrong detection** issue template.
