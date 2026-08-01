<<<<<<< HEAD
# OpenSeeFace Facetracking Wrapper

<div style="text-align: center;">

![logo](https://codeberg.org/ZRayEntertainment/Facetracker/raw/tag/25.2.1/facetracker/data/icons/hicolor/scalable/apps/de.z_ray.Facetracker.svg)

</div>

Simple wrapper UI for OpenSeeFace's facetracker.

- Start / Stop the tracker
- Select Webcam
- Select video mode (width, height, frames per second)
- Select tracking model used by the facetracker
- Set IP and Port for the tracker to listen

<div style="text-align: center;">

![screenshot](https://codeberg.org/ZRayEntertainment/Facetracker/raw/tag/25.2.1/facetracker/data/screenshots/facetracker.png)
![screenshot](https://codeberg.org/ZRayEntertainment/Facetracker/raw/tag/25.2.1/facetracker/data/screenshots/facetracker_2.png)
![screenshot](https://codeberg.org/ZRayEntertainment/Facetracker/raw/tag/25.2.1/facetracker/data/screenshots/facetracker_3.png)

</div>

### Download

<div style="text-align: center;">
<a href="https://flathub.org/apps/de.z_ray.Facetracker">
  <img width='240' alt='Download on Flathub' src='https://dl.flathub.org/assets/badges/flathub-badge-en.png'/>
</a>
</div>

[Flathub Build Project](https://github.com/flathub/de.z_ray.Facetracker)

## Development Requirements

- gcc
- cmake
- cairo-devel
- python3-devel
- python3-pip
- gobject-introspection-devel
- v4l-utils
- typelib-1_0-Gtk-4_0
- typelib-1_0-Adw-1

### Setup

#### Gnome Builder
- Install Builder
- Open Source Directory of Facetracker
- Run

#### Python / PyCharm
- Clone Repository
- Install
  - typelib-1_0-Gtk-4_0
  - typelib-1_0-Adw-1
- Provide osf pre-build binary (see below)
- `python3 facetracker/__init__.py`

### OpenSeeFace prebuild binary

To ease up flatpak distribution Facetracker uses OpenSeeFace's facetracker as a pre-build binary.  
Get is as follows:

- `git clone git@github.com:emilianavt/OpenSeeFace.git`
- `cd OpenSeeFace`
- `pip install onnxruntime opencv-python pillow numpy`
- `pip install -U pyinstaller`
- `pyinstaller ./facetracker.py`
- `cp models ./dist/facetracker/`

To test the pre-build locally create a symbolic link inside the source directory of Facetracker/facetracker/osf pointing
towards the dist directory of the pre-build.

# Webcams tested
The following cams have been tested with this application in functioning and gathering device capabilities properly

- NB Pro: BisonCam
- Logitec C922 Pro Stream Webcam
- USB3.0 capture (yes an actual capture card)
- Logitec HD WebCam C270
- pulsonic HDR webcam
- Integrated Camera of Lenovo V15 G4 AMN

---

# Facetracker-Packaged

Linux packaging for [Facetracker](https://github.com/Z-Ray-Entertainment/Facetracker) — a graphical user interface for OpenSeeFace that turns webcam input into face tracking data, useful for VTubbing and other avatar-driven applications.

Built and published automatically via GitHub Actions.

## Available formats

| Format | File | Use case |
|---|---|---|
| AppImage | `facetracker-x86_64.AppImage` | Universal (any distro, no install) |
| Debian | `facetracker_*_amd64.deb` | Debian, Ubuntu, Pop!_OS, Mint |
| RPM | `facetracker-*.x86_64.rpm` | Fedora, RHEL, openSUSE |
| Pacman | `facetracker-*.pkg.tar.zst` | Arch, Manjaro, EndeavourOS |

## Installation

### AppImage

```bash
chmod +x facetracker-x86_64.AppImage
./facetracker-x86_64.AppImage
```

### Debian / Ubuntu

```bash
sudo dpkg -i facetracker_*_amd64.deb
sudo apt-get install -f
```

### RPM

```bash
sudo rpm -i facetracker-*.x86_64.rpm
```

### Pacman

```bash
sudo pacman -U facetracker-*.pkg.tar.zst
```

## Required system dependencies

These are not bundled and must be installed via the system package manager:

- `python3`, `python3-gi`, `python3-pil`, `python3-numpy`
- `gtk4`, `libadwaita`
- `v4l-utils` (for webcam detection)

### OpenSeeFace

Facetracker is a UI for [OpenSeeFace](https://github.com/emilianavt/OpenSeeFace). You need the OpenSeeFace tracker installed separately — Facetracker will look for the `facetracker` binary on `PATH` (or under the `osf/` subdirectory if running from source).

## Upstream

- Repository: <https://github.com/Z-Ray-Entertainment/Facetracker>
- Upstream mirror: <https://codeberg.org/ZRayEntertainment/Facetracker>
- License: MIT

## License of the packaging files

The packaging files in this repository are provided under the MIT license (matching upstream).

_Generated with AI assistance_
