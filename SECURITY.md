# Security Policy

## Supported versions

Security fixes are applied to the latest version on the default branch.

## Reporting a vulnerability

Use GitHub's private vulnerability-reporting feature for this repository if it is enabled. In the repository, open **Security**, then **Advisories**, and choose **Report a vulnerability**.

If private reporting is unavailable, open a minimal issue that asks the maintainer for a private contact method. Do not include API keys, personal information, working exploit details, or other secrets in a public issue.

Include the affected browser and operating system, a concise description of the impact, and safe reproduction steps. Please allow a reasonable time for review before disclosing details publicly.

## Protecting API keys

Nihongo Story Reader is a static browser application and has no backend capable of hiding provider credentials. By default, keys are placed in `sessionStorage`. Selecting **Remember the key on this device** places the selected key in `localStorage`.

- Use restricted, low-limit, or easily revocable keys.
- Do not use remembered keys on a shared or untrusted device.
- Inspect custom provider endpoints before submitting a key.
- Never commit a key to this repository or paste one into an issue.
- Revoke and replace a key immediately if it may have been exposed.
- Clear the relevant browser site data when retiring a remembered key.

Provider requests leave the browser and are governed by that provider's security, privacy, retention, and billing policies.
