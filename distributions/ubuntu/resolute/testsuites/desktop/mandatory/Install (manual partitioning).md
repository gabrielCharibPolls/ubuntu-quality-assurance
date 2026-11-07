# Test Suite: Ubuntu Desktop – Install (manual partitioning)

## 1. Test Overview

| Field | Description |
|---|---|
| Test Suite | Ubuntu Desktop – Install (manual partitioning) |
| Category | Mandatory |
| Test Type | Functional / Compatibility / Usability |
| Operating System | Ubuntu |
| Release | 26.04 LTS – Resolute |
| Architecture | AMD64 |
| Environment | Virtual Machine |
| ISO Image | resolute-desktop-amd64.iso |
| Test Status | PASSED |
| Tester | Gabriel Charib |
| Results submitted | Yes – TestObserve |
| Submission date | 2026-11-07 |

## 2. Test Objectives

Validate the manual partitioning installation path.

Upstream reference: https://github.com/ubuntu/ubuntu-manual-tests/blob/main/stonking/testsuites/Ubuntu%20Desktop/Mandatory/Install%20(manual%20partitioning).md

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

## TC-INST-MANUAL-001 – Boot and Live Session Entry

**Objective:** Verify that the ISO boots into the live session and the installer starts.

**Test Steps:**

1. Boot the ISO image (GRUB: Try or install Ubuntu if shown).
2. Wait for the live session desktop.
3. Confirm the desktop installer opens automatically.

**Expected Results:**

- Live session boots successfully.
- Installer welcome UI is displayed.
- Welcome sound plays (when audio is available).

**Status:** TESTED

---

## TC-INST-MANUAL-002 – Language, Accessibility and Keyboard

**Objective:** Verify early installer configuration pages.

**Test Steps:**

1. Choose the desired language and click Next.
2. On Accessibility, exercise Seeing / Hearing / Typing / Pointing and clicking / Zoom options.
3. Choose the keyboard layout and click Next.

**Expected Results:**

- Language selection works.
- Accessibility controls are functional.
- Keyboard layout selection works.

**Status:** TESTED

---

## TC-INST-MANUAL-003 – Network and Install Path

**Objective:** Verify network connectivity page and Install Ubuntu selection.

**Test Steps:**

1. Connect to a network via the installer UI.
2. Click Next.
3. On Try or install Ubuntu, click Install Ubuntu.
4. Select Interactive installation and click Next.

**Expected Results:**

- Network connection succeeds.
- Install Ubuntu path is available.
- Interactive installation can be selected.

**Status:** TESTED

---

## TC-INST-MANUAL-004 – Applications and Optimise Pages

**Objective:** Verify application selection and optimise pages.

**Test Steps:**

1. On Applications, select Default selection and click Next.
2. On Optimise your computer, leave checkboxes unchecked and click Next.

**Expected Results:**

- Default application selection works.
- Optimise page advances without error.

**Status:** TESTED

## TC-INST-MANUAL-005 – Manual Partitioning Install

**Objective:** Verify manual disk layout installation.

**Test Steps:**

1. On Disk setup, select Manual installation.
2. Create the required partitions for Ubuntu.
3. Continue through encryption (No encryption), account, timezone and summary.
4. Install, reboot and log in.

**Expected Results:**

- Manual partitioning UI works.
- Custom layout is accepted.
- Installation completes and system boots.

**Status:** TESTED

---

# 5. Test Execution Summary

| Test ID | Test Case | Status | Bug ID |
|---|---|---|---|
| TC-INST-MANUAL-001 | Boot and Live Session Entry | TESTED | - |
| TC-INST-MANUAL-002 | Language, Accessibility and Keyboard | TESTED | - |
| TC-INST-MANUAL-003 | Network and Install Path | TESTED | - |
| TC-INST-MANUAL-004 | Applications and Optimise Pages | TESTED | - |
| TC-INST-MANUAL-005 | Manual Partitioning Install | TESTED | - |

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

**Overall Result:** PASS

**Total Test Cases:** 5

**Passed:** 5

**Failed:** 0

**Blocked:** 0

**Not Tested:** 0

### Final Assessment

Install (manual partitioning) completed successfully on Ubuntu 26.04 Resolute (AMD64, Proxmox VM). No defects were filed for this suite.

**Submitted to:** TestObserve  
**Date:** 2026-11-07  
**Result:** PASS
