# Documentation

- [Boat Instrument](https://philseeley.github.io/docs/boatinstrument/main.html)
- [Flutter-pi](https://github.com/ardera/flutter-pi?tab=readme-ov-file#flutter-pi)

# Repository Setup

Subscribe to the Debian repository:

```shell
sudo echo if password required

. /etc/os-release

curl https://philseeley.github.io/debian-ppa/phil.seeley.gpg.pem | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/phil.seeley.gpg

echo "deb https://philseeley.github.io/debian-ppa $VERSION_CODENAME main" | sudo tee /etc/apt/sources.list.d/phil.seeley.list >/dev/null

sudo apt update
```

# Installation

There are two flavours of installation, one for Desktop environments and one for dedicated instruments. The latter uses flutter-pi to render directly to the console without the need for X11/Wayland.

## Boat Instrument - Desktop

If you are running a desktop environment.

Debian bullseye(11) and bookworm(12) are supported for amd64 and arm64.

```shell
sudo apt install boatinstrument
```
If using a menu driven desktop (e.g. LXDE), the Boat Instrument can be found in the Utilities menu.

## Boat Instrument - flutter-pi

If you have a Raspberry PI with a dedicated screen that boots to the console.

Debian bullseye(11) and bookworm(12) are supported for amd64 and arm64.

**Note:** for bullseye(11) you need to enable "bullseye backports" to satisfy all dependencies.

```shell

echo "deb http://deb.debian.org/debian/ bullseye-backports main" | sudo tee /etc/apt/sources.list.d/bullseye-backports.list >/dev/null

sudo apt update
```

A bookworm(12) build for the "generic" \<type> is also supported for arm32.

To install:

```shell
sudo apt install boatinstrument-fpi-<type>
```
Where \<type> is one of:
- generic
- pi3 - arm64 only
- pi4 - arm64 only

The Boat Instrument is automatically started on TTY1 at boot, but can be disabled with:
```shell
sudo systemctl disable --now getty@tty1
```
