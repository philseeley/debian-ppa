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

## Boat Instrument - Desktop

Debian bullseye(11) and bookworm(12) are supported.

If you are running a desktop environment.

```shell
sudo apt install boatinstrument
```
If using a menu driven desktop (e.g. LXDE), the Boat Instrument can be found in the Utilities menu.

## Boat Instrument - flutter-pi

Debian bullseye(11) and bookworm(12) are supported.

If you have a Raspberry PI with a dedicated screen.

```shell
sudo apt install boatinstrument-f-pi-<type>
```
Where <type> is one of:
o generic
o pi3
o pi4

The Boat Instrument is automatically started on boot, but can be disabled with:
```shell
sudo systemctl disable --now getty@tty1
```
