# FFmpeg source archive for Hell Above

This repository exists to satisfy the **LGPL v3 source-code offer** for the FFmpeg build
distributed with the game *Hell Above* by Neotenic Media.

If you have a copy of Hell Above and want the source code for the FFmpeg it contains, this is
it. You do not need to contact us — everything is in this repository.

## What is in here

| File | What it is |
|---|---|
| `FFmpeg-f101fce22d64db10f500242e23e43a251fe14414.tar.gz` | Complete FFmpeg source, at the exact commit the shipped binary was built from. |
| `FFmpeg-Builds-latest-2026-08-20-1345.zip` | BtbN's FFmpeg-Builds scripts — the scripts used to control compilation. |
| `FFmpeg-Builds-master-2026-08-20-1345.zip` | As above, `master` branch snapshot. |

## Which binary this corresponds to

| | |
|---|---|
| FFmpeg version | `N-126229-gf101fce22d-20260820` |
| Upstream commit | `f101fce22d64db10f500242e23e43a251fe14414` |
| Build | BtbN FFmpeg-Builds, `win64-lgpl` variant |
| Licence | GNU Lesser General Public License, version 3 |
| Ships in the game at | `HellAbove_Data/StreamingAssets/ffmpeg/` |

The game uses FFmpeg **unmodified**, launched as a separate process to encode gameplay
recordings. No FFmpeg source has been altered, and FFmpeg is not linked into the game binary.

## Build configuration

The binary was built with the configuration below. Note it is deliberately **not** a GPL
build: `--enable-gpl` and `--enable-nonfree` are absent, and the GPL encoders `libx264` and
`libx265` are explicitly disabled. H.264 encoding is provided by `libopenh264` (BSD, Cisco).

```
--enable-version3 --enable-libopenh264 --disable-libx264 --disable-libx265
--disable-libxvid --disable-libxavs2 --disable-libfdk-aac
```

The complete configuration line is recorded in `THIRD-PARTY-NOTICES.txt` in the game build, and
is also printed by running `ffmpeg -buildconf` against the shipped executable.

## Rebuilding

The source and the build scripts above are sufficient to reproduce the binary. See BtbN's
FFmpeg-Builds documentation for how to run them.

## Upstream

- FFmpeg — <https://ffmpeg.org> / <https://github.com/FFmpeg/FFmpeg>
- BtbN FFmpeg-Builds — <https://github.com/BtbN/FFmpeg-Builds>
- OpenH264 — <https://www.openh264.org>

Neither Neotenic Media nor Hell Above is affiliated with or endorsed by the FFmpeg project.
