# Amnezia VPN 4.8.12.8 — Ubuntu 22.04 x64 distribution

Публичная публикация дистрибутива Amnezia VPN `4.8.12.8`, пересобранного на GitHub Actions `ubuntu-22.04` для совместимости с Ubuntu 22.04 / glibc 2.35.

## Source verification

- Upstream repository: <https://github.com/amnezia-vpn/amnezia-client/tree/4.8.12.8>
- Git tag: `4.8.12.8`
- Commit verified locally/upstream: `b591dd744558532bad8f4a8fa1f58221dcf2973a`
- Version field verified in `CMakeLists.txt`: `set(AMNEZIAVPN_VERSION 4.8.12.8)`
- Build runner: GitHub Actions `ubuntu-22.04`
- Compatibility gate: `objdump -p deploy/AppDir/service/bin/AmneziaVPN-service` contains no GLIBC symbols newer than `GLIBC_2.35`.

## Artifact

Скачайте файл из GitHub Release:

- `AmneziaVPN_4.8.12.8_Ubuntu_22.04_x64.tar.zip`

Содержимое ZIP:

- `AmneziaVPN_Linux_Installer.tar`
  - `AmneziaVPN_Linux_Installer.bin` — Qt Installer Framework Linux x64 installer

## Install on Ubuntu 22.04 x86_64

```bash
unzip -t AmneziaVPN_4.8.12.8_Ubuntu_22.04_x64.tar.zip
unzip AmneziaVPN_4.8.12.8_Ubuntu_22.04_x64.tar.zip
tar -xf AmneziaVPN_Linux_Installer.tar
chmod +x AmneziaVPN_Linux_Installer.bin
sudo ./AmneziaVPN_Linux_Installer.bin
```

Если на чистой Ubuntu 22.04 не хватает runtime-зависимости:

```bash
sudo apt-get update
sudo apt-get install -y libxkbcommon-x11-0
```

## Checksums

```text
bb90aa96b9b2c680f8344a246c8d1446cc14bae26a68d481b36ff15dafcbffcc  AmneziaVPN_4.8.12.8_Ubuntu_22.04_x64.tar.zip
0a6d6ac0f3e6f5a186fd25375b7f407988c6eea6ee9831f54894b2cfb10c91b4  AmneziaVPN_Linux_Installer.bin
78f91df41a1fa2f343d2d641b72350371f00b8c105c7d41f2b050b1a10224d17  AmneziaVPN-service
```

## Build evidence

- Workflow: `.github/workflows/build-ubuntu2204.yml`
- Successful run: <https://github.com/Mikhail2018/amnezia-vpn-4.8.12.8-ubuntu22.04-dist/actions/runs/28608940059>
