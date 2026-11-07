# Test Suite: Ubuntu Desktop – Install UEFI SecureBoot nVidia

## 1. Test Overview

| Field | Description |
|---|---|
| Test Suite | Ubuntu Desktop – Install UEFI SecureBoot nVidia |
| Category | Mandatory |
| Test Type | Functional / Compatibility / Usability |
| Operating System | Ubuntu |
| Release | 26.04 LTS – Resolute |
| Architecture | AMD64 |
| Environment | Virtual Machine |
| ISO Image | resolute-desktop-amd64.iso |
| Test Status | BLOCKED |
| Tester | Gabriel Charib |
| Results submitted | Yes – TestObserve |
| Submission date | 2026-11-07 |

> Note: Blocked: no NVIDIA GPU / Secure Boot NVIDIA target available in this Proxmox lab.

## 2. Test Objectives

Validate UEFI Secure Boot installation with NVIDIA proprietary drivers.

Upstream reference: https://github.com/ubuntu/ubuntu-manual-tests/blob/main/stonking/testsuites/Ubuntu%20Desktop/Mandatory/Install%20UEFI%20SecureBoot%20nVidia.md

## 3. Test Environment

### 3.1 Hardware / Virtual Machine

| Component | Configuration |
|---|---|
| CPU | QEMU Virtual CPU |
| RAM | 6 GB |
| Storage | 70 GB |
| Network | Ethernet |
| Virtualization | Proxmox |

### 3.2 Software

| Field | Value |
|---|---|
| ISO Image | resolute-desktop-amd64.iso |
| Release | Ubuntu 26.04 LTS – Resolute |
| Architecture | AMD64 |

# 4. Test Cases

## TC-INST-NV-001 – UEFI Secure Boot NVIDIA Install

**Objective:** Verify UEFI + Secure Boot install with NVIDIA proprietary drivers.

**Test Steps:**

1. Boot the ISO in UEFI mode with Secure Boot enabled on NVIDIA hardware.
2. Complete interactive installation with proprietary drivers as required by the upstream suite.
3. Reboot and verify NVIDIA modules load under Secure Boot.

**Expected Results:**

- Image boots in UEFI with Secure Boot.
- Installation completes.
- Proprietary NVIDIA drivers are installed and loaded.

**Status:** BLOCKED

**Blocker:** Lab environment is QEMU/KVM with Bochs VGA. No NVIDIA GPU and no Secure Boot NVIDIA validation target available.

---

# 5. Test Execution Summary

| Test ID | Test Case | Status | Bug ID |
|---|---|---|---|
| TC-INST-NV-001 | UEFI Secure Boot NVIDIA Install | BLOCKED | - |

## 6. Defect Reporting

If an unexpected result occurs:

1. Record the failing Test Case ID.
2. Describe the actual behavior.
3. Include the expected behavior.
4. Capture screenshots or terminal output.
5. Collect relevant system logs.
6. Check whether the issue is already reported.
7. Create a Launchpad bug report if appropriate.
8. Link the bug ID to the test result.

### Bug Report Template

- **Bug ID:**
- **Test Case ID:**
- **Summary:**
- **Severity:** Critical / High / Medium / Low
- **Priority:** High / Medium / Low
- **Steps to Reproduce:**
- **Expected Result:**
- **Actual Result:**
- **Reproducibility:** Always / Sometimes / Once
- **Logs / Evidence:**
- **Launchpad URL:**

## 7. Final Test Conclusion

**Overall Result:** BLOCKED

**Total Test Cases:** 1

**Passed:** 0

**Failed:** 0

**Blocked:** 1

**Not Tested:** 0

### Final Assessment

Suite blocked in the current Proxmox/QEMU lab (no NVIDIA hardware). To be re-run on a compatible UEFI Secure Boot NVIDIA machine.

**Submitted to:** TestObserve  
**Date:** 2026-11-07  
**Result:** BLOCKED
