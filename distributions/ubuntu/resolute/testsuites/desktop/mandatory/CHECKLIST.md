# Mandatory Desktop – Execution Checklist

Upstream source:
https://github.com/ubuntu/ubuntu-manual-tests/tree/main/stonking/testsuites/Ubuntu%20Desktop/Mandatory

Local documentation format:
`distributions/ubuntu/resolute/testsuites/desktop/mandatory/<Suite>.md`

Status values: `PASS` / `FAIL` / `BLOCKED` / `NOT TESTED` / `IN PROGRESS`

| Upstream suite | Local doc | Status | Bugs | Notes |
|---|---|---|---|---|
| Live Session | [Live Session.md](./Live%20Session.md) | PASS (2026-11-01) | — | Firefox portal noise noted as non-blocking |
| Install (entire disk) | [Install (entire disk).md](./Install%20(entire%20disk).md) | PASS (2026-11-07) | — | |
| Install (auto-resize) | [Install (auto-resize).md](./Install%20(auto-resize).md) | PASS (2026-11-07) | — | |
| Install (manual partitioning) | [Install (manual partitioning).md](./Install%20(manual%20partitioning).md) | PASS (2026-11-07) | — | |
| Install (entire disk with ZFS) | [Install (entire disk with ZFS).md](./Install%20(entire%20disk%20with%20ZFS).md) | PASS (2026-11-07) | — | |
| Install (entire disk with ZFS plus encryption) | [Install (entire disk with ZFS plus encryption).md](./Install%20(entire%20disk%20with%20ZFS%20plus%20encryption).md) | PASS (2026-11-07) | — | |
| Install (entire disk with TPM encryption) | [Install (entire disk with TPM encryption).md](./Install%20(entire%20disk%20with%20TPM%20encryption).md) | PASS (2026-11-07) | — | |
| Install no TPM option without TPM support | [Install no TPM option without TPM support.md](./Install%20no%20TPM%20option%20without%20TPM%20support.md) | PASS (2026-11-07) | — | QEMU/KVM without TPM |
| Install UEFI SecureBoot nVidia | [Install UEFI SecureBoot nVidia.md](./Install%20UEFI%20SecureBoot%20nVidia.md) | BLOCKED (2026-11-07) | — | No NVIDIA GPU in Proxmox lab |

## Campaign summary

| Result | Count |
|---|---|
| PASS | 8 |
| BLOCKED | 1 |
| FAIL | 0 |
| NOT TESTED | 0 |

## Format reminder (per suite file)

1. Test Overview table  
2. Test Objectives  
3. Test Environment  
4. Test Cases (`TC-…`) with Steps / Expected / Status  
5. Test Execution Summary (+ Bug ID column)  
6. Defect Reporting + Bug Report Template  
7. Final Test Conclusion (`PASS`/`FAIL`/`BLOCKED` counts)
