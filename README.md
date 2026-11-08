# Klia IPCam

View all your **ONVIF / RTSP IP cameras on a single screen**, with smooth GPU-accelerated video. Klia IPCam finds the cameras on your network, connects to them and shows them together in a grid. Your cameras and their passwords stay on your computer — nothing is sent to any cloud service.

## Features

- **Camera discovery** on your local network (WS-Discovery), or add a camera manually.
- **Grid view and full-quality view** — expand any camera to see its main stream.
- **PTZ controls** (pan, tilt, zoom) on cameras that support them.
- **Multi-lens cameras** — one cell per lens.
- **GPU decoding** with Vulkan Video, with an automatic OpenH264 software fallback when the GPU can't decode a stream.
- **Private by design** — passwords are stored in the system keyring (Secret Service portal); no accounts, no telemetry, no cloud.
- **Flatpak distribution** — sandboxed packaging for Linux x86_64.

## Installation

Download the latest `.flatpak` bundle from the [Releases](https://github.com/N3koSempai/ipcam/releases) page and install it:

```bash
flatpak install --user ./klia-ipcam-<version>.flatpak
```

Then launch **Klia IPCam** from your application menu, or run:

```bash
flatpak run io.github.N3kosempai.klia-ipcam
```

## Requirements

- Linux x86_64
- A GPU with Vulkan Video decoding support for hardware decoding (optional — software decoding is used otherwise)
- Cameras that speak ONVIF or provide an RTSP stream

## Supported video

- **H.264**: supported (GPU or software).
- **H.265 (HEVC)**: not supported yet. If a camera only offers H.265, the app can ask the camera to switch to H.264 from the setup wizard.

## Troubleshooting

- A camera shows **"Sin decodificador" / no decoder**: the OpenH264 runtime extension is missing. Install it with `flatpak install flathub org.freedesktop.Platform.openh264//2.5.1`.
- To force software decoding for testing, run with `KLIA_DECODER=software`.

## Community

- Found a bug or have a question? Open an [issue](https://github.com/N3koSempai/ipcam/issues).

---

This repository hosts the project page, releases and issue tracker for Klia IPCam.
