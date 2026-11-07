# DEF-002 – snapd-desktop-integration startup failure and Yaru theme CSS error

## Bug Report Template

- **Bug ID:** DEF-002
- **Test Case ID:** TC-LIVE-003 / Installed Desktop session startup
- **Summary:** snapd-desktop-integration fails once at session start (`Failed to open display`) with AppArmor portal denial, then recovers; later logs missing Yaru GTK CSS resource
- **Severity:** Low / Medium
- **Priority:** Low
- **Steps to Reproduce:**
  1. Boot Ubuntu 26.04.1 Desktop (QEMU/KVM, Wayland).
  2. Log into the Ubuntu GNOME session.
  3. Inspect logs:
     `journalctl -b --no-pager | grep -E 'snapd-desktop-integration|Theme parser error|Failed to open display|host.portal.Registry'`
- **Expected Result:** snapd-desktop-integration starts cleanly once, with no display open failure, no AppArmor deny on portal Register, and no missing theme CSS resource errors.
- **Actual Result:**
  - First start: `Failed to open display` → systemd user unit exits `status=2/INVALIDARGUMENT`.
  - Same timestamp: AppArmor DENIED on `org.freedesktop.host.portal.Registry` / `Register`.
  - Service restarts and becomes active.
  - Later: `Theme parser error: ... /com/ubuntu/themes/Yaru/4.0/gtk.css does not exist`
- **Reproducibility:** Observed on this boot/session (needs clean reboot confirmation)
- **Logs / Evidence:** `bugs/attachments/snapd-desktop-integration-journal.txt` (local QA workspace)
- **Launchpad URL:** TBD

## Launchpad draft

```text
Summary:
snapd-desktop-integration: first start fails with "Failed to open display" (AppArmor portal deny); Yaru 4.0 gtk.css missing

Package / snap:
snapd-desktop-integration 0.9 (rev 391), tracking latest/stable/ubuntu-26.04
snapd 2.77.1+ubuntu26.04.2

[Ubuntu release]
Ubuntu 26.04.1 LTS (resolute)

[Environment]
- Ubuntu GNOME Wayland
- QEMU/KVM, Bochs VGA
- Locale en_US.UTF-8

[Steps to reproduce]
1. Boot Ubuntu 26.04.1 Desktop
2. Log into GNOME Wayland
3. journalctl -b --no-pager | grep -E 'snapd-desktop-integration|Failed to open display|Theme parser error|host.portal.Registry'

[Expected behavior]
Daemon starts once without display failure or theme CSS import errors.

[Actual behavior]
1) First start fails:
   snapd-desktop-integration: Failed to open display
   systemd: ...service: Failed with result 'exit-code' (status=2)
   apparmor DENIED: org.freedesktop.host.portal.Registry Register
2) Service restarts and continues running.
3) Theme parser error:
   Failed to import: The resource at "/com/ubuntu/themes/Yaru/4.0/gtk.css" does not exist

[Impact]
Non-fatal: service recovers. Theme sync for snaps may be incomplete/noisy.
Suggested importance: Low (or Medium if theme sync is broken for snaps).

[Notes]
Observed in QEMU/Bochs guest. Not claiming all installs are affected.
Security checkbox: NO
```

## Versions

| Component | Version |
|---|---|
| snapd-desktop-integration | 0.9 (391) |
| snapd (deb) | 2.77.1+ubuntu26.04.2 |
| gtk-common-themes | 0.1-81-g442e511 (1535) |
