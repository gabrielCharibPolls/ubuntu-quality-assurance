# Ubuntu Quality Assurance

Manual quality assurance test suites for Ubuntu desktop releases.

This repository documents functional, compatibility, and usability validation
for Ubuntu Live Session, installer Mandatory suites, and related desktop scenarios.

Maintained as part of the **Ubuntu Quality** team.

## Scope

- Distribution: Ubuntu
- Release: 26.04 LTS (Resolute)
- Architecture: AMD64
- Environment: Virtual machine (Proxmox)
- Focus: Ubuntu Desktop Mandatory suites (Live Session + Install)

## Repository Structure

```text
distributions/
└── ubuntu/
    └── resolute/
        ├── testsuites/
        │   └── desktop/
        │       └── mandatory/
        │           ├── CHECKLIST.md
        │           ├── Live Session.md
        │           └── Install *.md
        └── defects/
            ├── README.md
            ├── DEF-001-...
            ├── DEF-002-...
            └── attachments/
```

## Test Suites

Upstream: [ubuntu-manual-tests / Ubuntu Desktop / Mandatory](https://github.com/ubuntu/ubuntu-manual-tests/tree/main/stonking/testsuites/Ubuntu%20Desktop/Mandatory)

| Suite | Category | Status |
|---|---|---|
| [Live Session](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Live%20Session.md) | Mandatory | PASS (2026-11-01) |
| [Install (entire disk)](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Install%20(entire%20disk).md) | Mandatory | PASS (2026-11-07) |
| [Install (auto-resize)](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Install%20(auto-resize).md) | Mandatory | PASS (2026-11-07) |
| [Install (manual partitioning)](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Install%20(manual%20partitioning).md) | Mandatory | PASS (2026-11-07) |
| [Install (entire disk with ZFS)](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Install%20(entire%20disk%20with%20ZFS).md) | Mandatory | PASS (2026-11-07) |
| [Install (entire disk with ZFS plus encryption)](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Install%20(entire%20disk%20with%20ZFS%20plus%20encryption).md) | Mandatory | PASS (2026-11-07) |
| [Install (entire disk with TPM encryption)](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Install%20(entire%20disk%20with%20TPM%20encryption).md) | Mandatory | PASS (2026-11-07) |
| [Install no TPM option without TPM support](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Install%20no%20TPM%20option%20without%20TPM%20support.md) | Mandatory | PASS (2026-11-07) |
| [Install UEFI SecureBoot nVidia](distributions/ubuntu/resolute/testsuites/desktop/mandatory/Install%20UEFI%20SecureBoot%20nVidia.md) | Mandatory | BLOCKED (no NVIDIA in lab) |
| [Mandatory checklist](distributions/ubuntu/resolute/testsuites/desktop/mandatory/CHECKLIST.md) | Mandatory | 8 PASS / 1 BLOCKED |

## Defects

| ID | Summary | Status |
|---|---|---|
| [DEF-001](distributions/ubuntu/resolute/defects/DEF-001-update-notifier-gtk-assertions.txt) | update-notifier GTK assertions | Draft ready |
| [DEF-002](distributions/ubuntu/resolute/defects/DEF-002-snapd-desktop-integration.md) | snapd-desktop-integration display/theme | Candidate |
| [Index](distributions/ubuntu/resolute/defects/README.md) | All findings | — |

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
