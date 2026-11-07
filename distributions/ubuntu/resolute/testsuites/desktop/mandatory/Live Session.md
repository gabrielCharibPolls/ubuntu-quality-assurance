# Test Suite: Ubuntu Desktop – Live Session

## 1. Test Overview

| Field | Description |
|---|---|
| Test Suite | Ubuntu Desktop – Live Session |
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
| Submission date | 2026-11-01 |

## 2. Test Objectives

Verify that the Ubuntu Desktop Live Session can be started and used correctly without installing the operating system.

The test campaign aims to validate:

- Boot and startup process.
- Language selection and localization.
- Desktop environment functionality.
- Default applications.
- Linux system commands.
- Network connectivity.
- Hardware compatibility.
- System stability.
- Basic security and permissions.

## 3. Test Environment

### 3.1 Hardware / Virtual Machine

| Component | Configuration |
|---|---|
| CPU | QEMU Virtual CPU |
| RAM |  6 GB|
| Storage | 70 GB |
| Network | Ethernet |
| Virtualization |  Proxmox  |

# 4. Test Cases

## TC-LIVE-001 – Live Session Startup

**Objective:** Verify that Ubuntu can boot successfully into the Live Session.

**Test Steps:**

1. Boot the ISO image.
2. Wait for the boot menu.
3. Select the default startup option.
4. Select the desired language.
5. Click Continue.
6. Select Try Ubuntu.
7. Wait for the desktop environment to load.

**Expected Results:**

- Boot screen is displayed.
- Language selection works.
- Installer interface is displayed correctly.
- Try Ubuntu option is available.
- Desktop environment loads successfully.
- No unexpected crash or boot error.

**Status:** TESTED

---

## TC-LIVE-002 – Desktop Environment

**Objective:** Verify the default desktop environment.

**Test Steps:**

1. Inspect the desktop.
2. Open the application launcher.
3. Open system settings.
4. Open the file manager.
5. Open the system menu.
6. Verify desktop navigation.
7. Test window management.

**Expected Results:**

- Desktop loads correctly
- Application launcher works
- System menu works
- Settings open without errors
- File manager opens
- Window management functions correctly

**Status:**  TESTED

---

## TC-LIVE-003 – Default Applications

**Objective:** Verify the functionality of applications included in the default Ubuntu installation.

### Application Test Matrix

| Application | Test | Expected Result | Notes |
|---|---|---|---|
| Firefox | Launch browser | Browser opens |Startup logs present (unsupported portal error under common/); UI OK.
| Files | Browse directories | Files and folders displayed |
| Terminal | Execute commands | Commands execute correctly |
| Text Editor | Create and save a file | File is saved |
| Document Viewer | Open a PDF | PDF displayed |
| Image Viewer | Open an image | Image displayed |
| Settings | Navigate settings | Settings accessible |
| Calculator | Perform calculations | Correct result |
| Archive Manager | Extract an archive | Files extracted |
| System Monitor | Inspect system resources | Metrics displayed |
| Software | Open software center | Interface loads |
| Help | Open documentation | Help interface loads |

**Additional Checks:**

- Applications open without crashing.
- No unexpected error messages.
- Windows can be closed correctly.
- Application menus are functional.

**Status:**  TESTED

---

## TC-LIVE-004 – Linux Command-Line Validation

**Objective:** Verify basic Linux commands and system utilities.

### A. Filesystem Commands

| Command | Test | Expected Result |
|---|---|---|
| `pwd` | Display current directory | Correct path |
| `ls -la` | List files | Directory listing |
| `mkdir qa-test` | Create directory | Directory created |
| `touch qa-test/test.txt` | Create file | File created |
| `cp` | Copy file | File copied |
| `mv` | Rename file | File renamed |
| `cat` | Read file | Content displayed |
| `rm` | Delete test file | File removed |

### B. System Information

| Command | Test | Expected Result |
|---|---|---|
| `uname -a` | Kernel information | Kernel details |
| `lsb_release -a` | Distribution information | Ubuntu release |
| `hostnamectl` | Host information | System details |
| `lscpu` | CPU information | CPU details |
| `free -h` | Memory usage | RAM information |
| `df -h` | Disk usage | Filesystem information |
| `lsblk` | Block devices | Storage devices |

### C. Process Management

| Command | Test | Expected Result |
|---|---|---|
| `ps aux` | List processes | Process list |
| `top` | Monitor processes | Live process information |
| `pgrep` | Search process | Matching PID |
| `systemctl` | Inspect services | Service information |
| `journalctl -b` | Inspect boot logs | Boot journal accessible |

### D. Network Commands

| Command | Test | Expected Result |
|---|---|---|
| `ip addr` | Inspect network interfaces | Interface information |
| `ip route` | Inspect routing table | Default route if connected |
| `ping -c 4 127.0.0.1` | Local network stack | Successful replies |
| `ping -c 4 1.1.1.1` | External connectivity | Replies if internet available |
| `getent hosts ubuntu.com` | DNS resolution | IP addresses returned |
| `curl -I https://ubuntu.com` | HTTP connectivity | HTTP response |

### E. Permissions and Security

| Command | Test | Expected Result |
|---|---|---|
| `whoami` | Current user | Correct username |
| `id` | User identity | UID and groups |
| `chmod` | Change permissions | Permissions updated |
| `stat` | Inspect file permissions | Metadata displayed |
| `sudo -v` | Check sudo authentication | Authentication succeeds if authorized |

**Important:** Commands that modify files or permissions must operate only on dedicated test files.

**Status:**  TESTED

---

## TC-LIVE-005 – Network Connectivity

**Objective:** Verify network functionality.

**Test Steps:**

1. Inspect available network interfaces.
2. Test Ethernet connectivity if available.
3. Test DNS resolution.
4. Open Firefox.
5. Browse an HTTPS website.
6. Disconnect and reconnect the network.

**Expected Results:**

- Network interfaces are detected.
- Network connection works.
- DNS resolution works.
- Web browsing works.
- Reconnection is successful.

**Status:**  TESTED

---

## TC-LIVE-006 – Hardware Compatibility

**Objective:** Verify hardware detection and basic functionality.

| Component | Test | Expected Result |
|---|---|---|
| CPU | `lscpu` | CPU detected |
| RAM | `free -h` | Memory detected |
| GPU | `lspci` | Graphics device detected |
| Keyboard | Type text | Input works |
| Mouse | Move and click | Input works |
| Display | Change resolution | Display updates |


**Status:**  TESTED

---

## TC-LIVE-007 – System Stability

**Objective:** Verify that the Live Session remains stable during normal usage.

**Test Steps:**

1. Open multiple applications.
2. Switch between applications.
3. Open multiple terminal sessions.
4. Browse the internet.
5. Monitor CPU and RAM usage.
6. Leave the system running for at least 30 minutes.
7. Close all applications.

**Expected Results:**

- No unexpected system freeze.
- No unexpected application crashes.
- Desktop remains responsive.
- System resources are reported correctly.

**Status:**  TESTED

---

## TC-LIVE-008 – Session Shutdown

**Objective:** Verify that the Live Session can be terminated correctly.

**Test Steps:**

1. Open the system menu.
2. Select Power Off.
3. Confirm shutdown.
4. Observe the shutdown process.

**Expected Results:**

- Shutdown dialog is displayed.
- System shuts down correctly.
- No unexpected shutdown error.

**Status:**  TESTED

---

# 5. Test Execution Summary

| Test ID | Test Case | Status | Bug ID |
|---|---|---|---|
| TC-LIVE-001 | Live Session Startup | TESTED | - |
| TC-LIVE-002 | Desktop Environment | TESTED | - |
| TC-LIVE-003 | Default Applications | TESTED | - |
| TC-LIVE-004 | Linux Commands | TESTED | - |
| TC-LIVE-005 | Network Connectivity | TESTED | - |
| TC-LIVE-006 | Hardware Compatibility | TESTED | - |
| TC-LIVE-007 | System Stability | TESTED | - |
| TC-LIVE-008 | Session Shutdown | TESTED | - |

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

**Total Test Cases:** 8

**Passed:** 8

**Failed:** 0

**Blocked:** 0

**Not Tested:** 0

### Final Assessment

All 8 mandatory Live Session test cases were executed successfully on Ubuntu 26.04 Resolute (AMD64, Proxmox VM). One non-blocking observation was recorded for Firefox startup logs (unsupported portal under common/); UI functionality was unaffected. No defects were filed for this suite.

**Submitted to:** TestObserve  
**Date:** 2026-11-01  
**Result:** PASS
