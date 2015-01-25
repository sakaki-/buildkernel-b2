# buildkernel-b2
Script to build a bootable Linux kernel for the Excito B2.

## Description

<img src="https://raw.githubusercontent.com/sakaki-/resources/master/excito/b2/Excito_b2.jpg" alt="Excito B2, aka Bubba|TWO" width="250px" align="right"/>
**buildkernel-b2** is a script that builds a Gentoo Linux kernel image suitable for booting either from the B2's internal disk (default), or from a USB key (when the **--usb** option is specified).

It is useful when targeting a B2 system with:
* the default U-Boot settings in flash memory; and
* a payload kernel that has size > 4MiB uncompressed (or > 2MiB compressed).

**buildkernel-b2** should be run as root, in the top level kernel source directory. You will need an appropriate `.config` file in place when building the kernel (which must have had the [gentoo-b2-kernel-patches](https://github.com/sakaki-/gentoo-b2-kernel-patches) patchset applied; the kernel provided by [gentoo-b2-sources](https://github.com/sakaki-/gentoo-b2-overlay/tree/master/sys-kernel/gentoo-b2-sources) from the [gentoo-b2](https://github.com/sakaki-/gentoo-b2-overlay) overlay is suitable, for example).

You can run **buildkernel-b2** either on the B2 directly, or on a Gentoo PC (with an appropriately configured `crossdev` setup).

If running on a PC, a directory `deploy_root` will be created as a result of running the script, with the necessary files for you to copy across to your B2.

If running on the B2 natively, the files (kernel, modules, DTB, config and System.map) will be moved to the correct positions for you (and prior copies of all but the modules backed up).

Please see the included manpage for further details.

## Installation

**buildkernel-b2** is best installed (on Gentoo) via its ebuild, available as part of the [**gentoo-b2** overlay](https://github.com/sakaki-/gentoo-b2-overlay).
