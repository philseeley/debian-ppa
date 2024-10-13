# Repository Setup

Subscribe to the Debian repository:

```shell
sudo echo if password required

curl https://philseeley.github.io/debian-ppa/phil.seeley.gpg.pem | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/phil.seeley.gpg

echo 'deb https://philseeley.github.io/debian-ppa bookworm main' | sudo tee /etc/apt/sources.list.d/phil.seeley.list >/dev/null

sudo apt update
```

# Installation

## Boat Instrument - Desktop

If you are running a desktop environment.

```shell
sudo apt install boatinstrument
```
If using a menu driven desktop (e.g. LXDE), the Boat Instrument can be found in the Utilities menu.

## Boat Instrument - flutter-pi

If you have a Raspberry PI with a dedicated screen.

```shell
sudo apt install boatinstrument-flutter-pi
```
The Boat Instrument is automatically started on boot, but can be disabled with:
```shell
sudo systemctl disable --now boatinstrument-flutter-pi
```
