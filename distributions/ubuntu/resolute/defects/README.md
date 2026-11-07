# Defects – Ubuntu 26.04 Resolute (AMD64)

Defects found during Ubuntu Desktop QA on Proxmox/QEMU.

| ID | Summary | Package / Snap | Severity | Status | Launchpad | Linked suite |
|---|---|---|---|---|---|---|
| DEF-001 | Repeated `gtk_widget_get_scale_factor` GTK assertions | `update-notifier` 3.207.2 | Low | Draft ready | TBD | Post-install / Installed Desktop |
| DEF-002 | First start fails (`Failed to open display`) + AppArmor portal deny; Yaru theme CSS missing | `snapd-desktop-integration` 0.9 (rev 391) | Low / Medium | Candidate | TBD | Live Session / Installed Desktop |
| DEF-003 | One-shot `g_variant_unref` assertion at login | `gnome-settings-daemon` / `gsd-keyboard` 50.0-1ubuntu1 | Low | Candidate (weak) | TBD | Installed Desktop |
| DEF-004 | Nautilus missing unwritable emblem (spelling: `unwritable` vs Yaru `unwriteable`) | `nautilus` 1:50.2.2-0ubuntu0.2 / `yaru-theme-icon` | Low | **Strong candidate** | TBD | TC-LIVE-003 Files |
| DEF-005 | AppArmor DENIED `/proc/sys/vm/max_map_count` every ~3h | `firmware-updater` snap rev 262 | Low | Candidate | TBD | Installed Desktop |
| DEF-006 | AppArmor DENIED read of existing `/etc/paperspecs` | `cups` / `cupsd` | Low | Candidate | TBD | Printing |
| DEF-007 | snap-store spam `ratings.ubuntu.com` Connection refused (~357 lines) | `snap-store` snap rev 1468 | Low / unclear | Needs network check | TBD | TC-LIVE-003 Software |

## Environment (common)

| Field | Value |
|---|---|
| OS | Ubuntu 26.04.1 LTS (resolute) |
| Arch | AMD64 |
| Virt | QEMU/KVM (Proxmox), Bochs VGA |
| Session | Ubuntu GNOME on Wayland |
| Capture date | 2026-11-07 |

## Notes

- DEF-001 already has a Launchpad-ready description under local `ubuntu-qa/bugs/`.
- DEF-002 is the strongest next candidate (clear failure + recovery + theme error).
- Noise **not** filed as bugs: chrony IPv6 `No route to host`, KHO kexec scratch, Bochs “not hardware accelerated”, `/dev/sr0 Can't open blockdev`, transient wrong-password auth failures.
