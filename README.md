# OpenStick platform

How OpenStick's open layer is integrated into the partner's certified Android TV platform.

OpenStick runs on a certified Android TV / Google TV platform supplied by a manufacturing partner ([decision 0008](https://github.com/opensticktv/openstick/blob/main/decisions/0008-certified-base-open-layer.md)). The bootloader, Android core, DRM and Google services are the partner's and Google's, and are locked so 4K streaming works. This repo holds what OpenStick controls:

- `docs/system-apps.md`: the OpenStick apps preinstalled on the device and the privileges each needs
- Partner integration notes and requirements (added once a partner is chosen)

The earlier plan for a fully open Linux image is in the history of this repo and in [PRD.open-linux-edition.md](https://github.com/opensticktv/openstick/blob/main/docs/PRD.open-linux-edition.md).
