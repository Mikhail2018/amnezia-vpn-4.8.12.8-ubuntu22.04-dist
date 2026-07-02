# Amnezia VPN 4.8.12.8 — Ubuntu 22.04 x64 distribution

Публичная публикация Linux x64 дистрибутива Amnezia VPN `4.8.12.8`.

> ⚠️ Compatibility note: the initially mirrored upstream binary was later found to require `GLIBC_2.38`, while Ubuntu 22.04 ships glibc `2.35`. On Ubuntu 22.04 this can crash `AmneziaVPN-service` at startup. Use Ubuntu 24.04 for this binary, or rebuild Amnezia from source on Ubuntu 22.04/glibc 2.35.

## Source verification

- Upstream repository: <https://github.com/amnezia-vpn/amnezia-client/tree/4.8.12.8>
- Git tag: `4.8.12.8`
- Commit verified locally: `b591dd744558532bad8f4a8fa1f58221dcf2973a`
- Version field verified in `CMakeLists.txt`: `set(AMNEZIAVPN_VERSION 4.8.12.8)`

## Artifact

Скачайте файл из GitHub Release:

- `AmneziaVPN_4.8.12.8_Ubuntu_22.04_x64_distribution.zip`

Содержимое ZIP:

- `AmneziaVPN_Linux_Installer.bin` — Qt Installer Framework Linux x64 installer
- `SHA256SUMS` — checksum installer file
- `README_UBUNTU_22.04_RU.txt` — локальная инструкция установки

## Install / compatibility

```bash
unzip -t AmneziaVPN_4.8.12.8_Ubuntu_22.04_x64_distribution.zip
unzip AmneziaVPN_4.8.12.8_Ubuntu_22.04_x64_distribution.zip
sha256sum -c SHA256SUMS
chmod +x AmneziaVPN_Linux_Installer.bin
sudo ./AmneziaVPN_Linux_Installer.bin
```

Если на чистой Ubuntu 22.04 не хватает runtime-зависимости:

```bash
sudo apt-get update
sudo apt-get install -y libxkbcommon-x11-0
```

## Checksums

Full distribution ZIP:

```text
b0e3d3399f394bfa2988bbb207f141fd1cf6edc78e89bcc2b9404a6ce66c8281  AmneziaVPN_4.8.12.8_Ubuntu_22.04_x64_distribution.zip
```

Installer inside ZIP:

```text
6990efcb2939af4a87b473feeab2240df581efebe5270a6f16dff38f05a3ab7b  AmneziaVPN_Linux_Installer.bin
```

## Notes

This repository is a convenience distribution mirror for a specific Amnezia VPN release artifact and installation notes. Amnezia VPN source code belongs to the upstream project linked above.
