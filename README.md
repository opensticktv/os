# OpenStick OS

The OpenStick device image: a signed, A/B-updatable Linux on a Debian userland with a (near-)mainline kernel, booting straight into the 10-foot launcher.

Status: v0 prototype. The build system is not chosen yet ([decision 0003](https://github.com/opensticktv/openstick/blob/main/decisions/0003-image-build-system.md)); `recipes/` is empty until it is.

## Layout

| Path | Contents |
| --- | --- |
| `boards/` | One folder per board: kernel config fragment, device tree, patches, bootloader notes, test results |
| `overlay/` | Files copied into every image (systemd units, compositor config, defaults) |
| `recipes/` | Image build recipes (debos or mkosi) |
| `docs/` | Partition layout, first-run flow, recovery |

## Boards

| Board | Role | Status |
| --- | --- | --- |
| [orangepi-zero2w](boards/orangepi-zero2w/) | v0 prototype | Out-of-tree HDMI and Cedrus patches needed |
| [cm5-tvstick](boards/cm5-tvstick/) | v1 candidate (compact stick, no 4K YouTube) | Spike |
| [rk3588](boards/rk3588/) | v1 candidate (4K native playback) | Spike |
| [x86-n100](boards/x86-n100/) | v1 candidate (4K native and in Chrome) | Spike |

## Components in the image

cage (Wayland kiosk compositor), PipeWire, GStreamer and ffmpeg with v4l2-request or VA-API, Kodi, Flatpak, BlueZ, libCEC, RAUC, FCast receiver, UxPlay, MiracleCast (experimental), DLNA renderer, `openstickd`, the launcher. Google Chrome is **not** in the image; it is installed on first run into the `vendor` partition ([decision 0002](https://github.com/opensticktv/openstick/blob/main/decisions/0002-google-chrome-for-web-apps.md)).
