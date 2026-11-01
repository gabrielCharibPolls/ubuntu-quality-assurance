# Ubuntu Quality Assurance

Manual quality assurance test suites for Ubuntu desktop releases.

This repository documents functional, compatibility, and usability validation
for Ubuntu Live Session and related desktop scenarios.

Maintained as part of the **Ubuntu Quality** team.

## Scope

- Distribution: Ubuntu
- Release: 26.04 LTS (Resolute)
- Architecture: AMD64
- Environment: Virtual machine (Proxmox)
- Focus: Live Session (no installation required)

## Repository Structure

```text
distributions/
└── ubuntu/
    └── resolute/
        └── testsuites/
            └── desktop/
                └── mandatory/
                    └── Live Session.md
```

## Test Suites

| Suite | Category | Status |
|---|---|---|
| [Live Session](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Live%20Session.md) | Mandatory | In progress |

## How to Use

1. Open the relevant test suite document.
2. Prepare the test environment described in the suite.
3. Execute each test case in order.
4. Record results (`PASS` / `FAIL` / `BLOCKED` / `NOT TESTED`).
5. Document defects using the bug report template in the suite.
6. Link Launchpad bugs when applicable.

## Result Status

| Status | Meaning |
|---|---|
| `PASS` | Expected results achieved |
| `FAIL` | Unexpected behavior observed |
| `BLOCKED` | Execution could not continue |
| `NOT TESTED` | Not executed yet |

## Defect Reporting

When a test fails:

1. Capture steps to reproduce
2. Record expected vs actual results
3. Attach screenshots and relevant logs
4. Check for existing Launchpad reports
5. File a new bug if needed and link the bug ID in the suite

## Conventions

- One test suite per Markdown file
- Keep mandatory suites high-level and reproducible
- Put detailed command/application matrices only where needed
- Use Notes for non-blocking observations (e.g. startup log noise)
