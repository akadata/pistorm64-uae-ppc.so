# qemu-uae.so (PPC support library for PiStorm64)

This repository contains a single shared library: `qemu-uae.so`.

It is required for building and running the **PPC support path** used by PiStorm64 when booting AmigaOS 4.x Classic (and other PPC workloads) via the UAE/QEMU-PPC bridge. Without this library present, PPC support cannot be compiled or linked correctly.

This repo exists so the correct `qemu-uae.so` can be pinned, shared, and reproduced across systems.

## What this is

- `qemu-uae.so` is a shared object used by PiStorm64 to provide PPC emulation support.
- It is typically installed on the build host at: `/usr/local/lib/qemu-uae.so`
- PiStorm64 expects to link against it (or load it) when PPC support is enabled.

## What this is not

- This repository is **not** the full PiStorm64 emulator.
- This repository does **not** include AmigaOS files, ROMs, or any proprietary components.

## Files

- `qemu-uae.so` — the PPC emulation support library required by PiStorm64.


## Provenance

This `qemu-uae.so` binary was built on a **Raspberry Pi 4 (aarch64, 64-bit)** from the FS-UAE QEMU-UAE plugin source:

- FS-UAE plugin: `https://github.com/FrodeSolheim/fs-uae-plugin-qemu-uae.git`
- QEMU-UAE submodule used by the plugin: `https://github.com/FrodeSolheim/qemu-uae.git`

The resulting library was installed as `/usr/local/lib/qemu-uae.so` and then copied into this repository to provide a known-good artifact for PiStorm64 builds.

## Using this library

### Option A: install to the standard location

Copy the library into place and refresh the loader cache:

```sh
sudo install -m 0755 qemu-uae.so /usr/local/lib/qemu-uae.so
sudo ldconfig
```

# Install
```git clone https://github.com/akadata/pistorm64-uae-ppc.so.git
cd pistorm64-uae-ppc.so
sudo install -m 0755 qemu-uae.so /usr/local/lib/qemu-uae.so
sudo ldconfig```

# boot.log

See boot.log for proof of concept and Good luck, it almost boots on A500 with PiStorm boards

