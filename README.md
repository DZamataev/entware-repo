# Entware Repository for Keenetic

Custom Entware package repository for Keenetic routers.

## Supported Architectures

| Architecture | Devices |
|--------------|---------|
| `mipsel-3.4-kn` | Keenetic with MIPS Little Endian (MT7621, etc.) |
| `mips-3.4-kn` | Keenetic with MIPS Big Endian (MT7628, etc.) |
| `aarch64-3.10-kn` | Keenetic with ARM64 (KN-1811, etc.) |

## Installation

### 1. Determine your architecture

```bash
opkg print-architecture
# mipsel -> use mipsel-3.4-kn
# mips   -> use mips-3.4-kn
# aarch64 -> use aarch64-3.10-kn
```

### 2. Add repository

Create file `/opt/etc/opkg/custom.conf`:

```bash
# For mipsel:
echo "src/gz keenetic_custom https://dzamataev.github.io/entware-repo/mipsel-3.4-kn" >> /opt/etc/opkg/custom.conf

# For mips:
echo "src/gz keenetic_custom https://dzamataev.github.io/entware-repo/mips-3.4-kn" >> /opt/etc/opkg/custom.conf

# For aarch64:
echo "src/gz keenetic_custom https://dzamataev.github.io/entware-repo/aarch64-3.10-kn" >> /opt/etc/opkg/custom.conf
```

### 3. Update and install

```bash
opkg update
opkg install awg-manager          # Web-интерфейс для AmneziaWG
opkg install sing-box-awg         # sing-box stable
opkg install sing-box-awg-beta    # sing-box beta
opkg install smtp-tunnel-client   # SOCKS5 proxy через SMTP
```


## Use only if understand what are you doing
