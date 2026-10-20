# Partition layout

| Partition | Mode | Contents | Updated by | Wiped by factory reset |
| --- | --- | --- | --- | --- |
| `boot` | read-only | Bootloader, kernel, device tree, boot counter | RAUC | No |
| `rootfs-A` / `rootfs-B` | read-only, signed | OS image | RAUC (A/B swap) | No |
| `recovery` | read-only | Minimal recovery system: roll back, factory reset, re-download OS | Rarely, by RAUC | No |
| `vendor` | writable | Google Chrome (current + previous) | `chrome-updater` service | Yes |
| `data` | writable | Settings, app data, Flatpak apps, pairing tokens | Apps and `openstickd` | Yes |

A boot counter falls back to the other rootfs slot after three failed boots.
