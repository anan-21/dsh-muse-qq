# Standalone extraction and verification

Source baseline: `muse-qq-bridge` commit
`cdb4fccb5a41457c5d04b01854c1775c8d2e91f1`, tracked DSH/Muse files only.
No unrelated Git history, live state, account information or credentials copied.

## Scope

- Runtime, local routing, context export and private API behavior remain the same.
- Flatten the feature directory to the repository root and update installation,
  helper templates, test discovery and document links accordingly.
- No application UI, database migration, account login or server deployment.
- Publish independently under MIT with the original and upstream notices.
- Keep a migration link in the former repository; maintain one active source.

## Acceptance

| ID | Requirement | Status |
| --- | --- | --- |
| S1 | Extract only tracked feature files, preserving runtime layout and license | Verified |
| S2 | Root-relative installation, helper and test paths work independently | Verified locally and in CI |
| S3 | All 85 offline checks and independent Linux/macOS CI pass | Verified on both platforms |
| S4 | Clean initial history, public commit identity, no private runtime files | Verified before publication |
| S5 | New GitHub repository published and old entry points link here | Published; original migration merged |

## Evidence boundaries

The original feature passed its 85 offline checks and the source repository's
Linux CI. Those results are historical provenance; this extraction runs the
standalone tests again. No real QQ/DSH/Muse account acceptance is claimed.

Current CI: [Tests](https://github.com/anan-21/dsh-muse-qq/actions/workflows/tests.yml).
Detailed verification commands are in [CONTRIBUTING.md](CONTRIBUTING.md).

Local extraction gate: 45 root Python tests, 5 installer tests and 35 Node tests
passed on macOS. Compilation, Bash syntax and project-rule validation passed.
Independent review found zero broken relative Markdown links, retained hook
executable mode and seven runtime files byte-identical to the source baseline.

Published gate for extracted source `1b1a76dcd983eb02cf4a401031e36907ff8b6e99`:
[Linux and macOS CI](https://github.com/anan-21/dsh-muse-qq/actions/runs/42449272004)
succeeded. The original repository's
[migration PR](https://github.com/anan-21/muse-qq-bridge/pull/6) also passed its
bridge regression gate and was merged. Original Git history is retained there;
this repository has a clean initial source history with public noreply identities.
