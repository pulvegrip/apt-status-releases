# apt-status releases

Release assets of **apt-status**, a read-only APT fleet-status collector for
Debian-family hosts (Ubuntu 24.04/26.04, Debian 13, Raspberry Pi OS and
Debian-based Armbian Bookworm/Trixie). It never changes package state and
never runs `apt update`.

This repository holds published releases only. Each release has three assets:
- `apt-status-X.Y.Z.tar.gz` (the application)
- `install.sh` (installer/updater)
- `SHA256SUMS`

They are built and checksummed by the release workflow of the (private)
source repository and copied here unchanged.

## Install or update

```sh
curl -fsSLO https://github.com/pulvegrip/apt-status-releases/releases/latest/download/install.sh
sudo sh install.sh                 # install, or update to the latest release
sudo sh install.sh --version X.Y.Z # a specific release
sh install.sh --check              # installed vs latest
```

`install.sh` verifies the archive against `SHA256SUMS` and checks that the
host is a supported target before it changes anything. To verify manually:
download all three assets and run `sha256sum -c SHA256SUMS`.

Prerequisites on the host: `python3` (≥ 3.11) and `python3-apt`.
