# armbian-onecloud
[![build](https://img.shields.io/github/actions/workflow/status/hzyitc/armbian-onecloud/ci.yml)](https://github.com/hzyitc/armbian-onecloud/actions/workflows/ci.yml) [![downloads](https://img.shields.io/github/downloads/hzyitc/armbian-onecloud/total)](https://github.com/hzyitc/armbian-onecloud/releases) [![downloads@latest](https://img.shields.io/github/downloads/hzyitc/armbian-onecloud/latest/total)](https://github.com/hzyitc/armbian-onecloud/releases/latest)

[README](README.md) | [中文文档](README_zh.md) | [安装文档](INSTALL.md)

**All changes were push to [the official repository](https://github.com/armbian/build).**

## First-login

Hostname: `onecloud`

Account:  `root`

Password: `1234`

## Build Parameters

### `BOARD`=`onecloud`

### `BRANCH`={`edge`,`current`,`legacy`}

| BRANCH    | kernel version | eMMC | HDMI | VPU |
| :-:       | :-:            | :-:  | :-:  | :-: |
| `edge`    | `v6.1`         | ✔️¹  | ✔️² | ✔️² |
| `current` | `v5.15`        | ✔️¹  | ✔️² | ✔️² |
| `legacy`  | `v5.10`        | ✔️¹  | ✔️² | ✔️² |

> ¹: Need a patch
>
> ²: Use patch to support

## How to boot from `u-boot` ?

### Boot from `USB`

```
setenv bootdev "usb 0"
usb start
fatload ${bootdev} 0x20800000 boot.scr && autoscr 0x20800000
```

### Boot from `eMMC`

```
setenv bootdev "mmc 1"
fatload ${bootdev} 0x20800000 boot.scr && autoscr 0x20800000
```

## `GPIO`

In the board, there is a missing 44-pins chip (WiFi module possibly) which has lots of pins connected to the `SoC`. They are ablt to be used as `GPIO`.

Please check the `dts` (added by `patch/kernel/meson-{edge,current,legacy}/board_onecloud/0001-add-dts.patch`) for more details.

NOTE: These pins were found in `V1.0 board`. Those in `V1.3 board` was not confirmed yet.

## Related link

[`armbian/build`](https://github.com/armbian/build) - Armbian offical

[`xdarklight/linux@meson-mx-integration-5.18-20220417`](https://github.com/xdarklight/linux/tree/meson-mx-integration-5.18-20220417) - the source of `HDMI` patch

[`S805_Datasheet V0.8 20150126.pdf`](https://dn.odroid.com/S805/Datasheet/S805_Datasheet%20V0.8%2020150126.pdf) - S805 datasheet
