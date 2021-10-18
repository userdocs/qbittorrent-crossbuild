## qBittorrent crossbuild deb packages for Debian based systems.

This intends to serves as a testing and demonstration repo for qbittorrent and QT6.

### Info

Builds libtorrent `RC_2_0` + `QT6` + `qBittorrent` master packaged into a deb file.

- Libtorrent and qBittorrent installed to - `/usr/local`

- QT6 installed to - `/opt/QT6`


### Install dependencies

There are builds for either the desktop version `qbittorrent` or the webui only version `qbittorrent-nox`

#### qbittorrent-nox (webui)

```bash
apt install -y zlib1g libgeoip1
```

#### qbittorrent (desktop)

```bash
apt install -y zlib1g libgeoip1 libglu1-mesa libopengl0 libxcb-xinput0
```

### Environment settings

If you need root to install the deb you may need to use this command:

```bash
export PATH=/sbin:/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin
```

QT6 library path

We are using QT6 and it's probably going to cause problems if loaded into `/usr/local/` therefore it is installed to `/opt/QT6` so we need to se this in the environment to load the libraries.

```bash
export LD_LIBRARY_PATH="/opt/QT6/lib:/usr/local/lib${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}"
```

### Downloads:

Example download using Debian Bullseye amd64.

```
wget https://github.com/userdocs/qbittorrent_crossbuild/releases/download/4.4.0beta3_2.0.4.0/debian-bullseye-qbittorrent-amd64.deb
```

Check the release for all downloads

https://github.com/userdocs/qbittorrent_crossbuild/releases/latest

### Installation

Install it:

```bash
dpkg -i debian-bullseye-qbittorrent-amd64.deb
```

### Supported OS:

- Debian Buster
- Debian Bullseye
- Ubuntu Focal
- Ubuntu Hirsute

### Supported Arch:

- armhf
- aarch64
- amd64
