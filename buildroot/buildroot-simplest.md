# buildroot simplest example

## preparing system

```
# apt install libncurses-dev
# apt install libdt4-dev
```

## get buildroot

```
$ git clone git://git.busybox.net/buildroot
$ cd buildroot/
$ make help
$ make help list-defconfigs
$ make help list-defconfigs  | grep wandboard
$ make wandboard_defconfig
```

## menuconfig

```
buildroot/.config

$ make menuconfig

Target options
  [*] Enable NEON SIMD extension support
  [*] Enable VFP extension support
      Target ABI (EABIhf)  --->
      ARM instruction set (Thumb2)  --->

Build options
  [*] Enable compiler cache

Toolchain
  [*] Enable C++ support
  [*] Purge unwanted locales

System configuration
  (mini-dynak) System hostname
  (Welcome to Dynak Mini Linux) System banner
  [*] Enable root login with password
  (rootroot) Root password
  (projekt/custom.sh) Custom scripts to run before creating filesystem images

Target packages
      Networking applications  --->
        [*] apache
        [*] ethtool
      Development tools  --->
        [*] git
```

## sdcard

```
pv sdcard.img | dd of=/dev/sdb bs=4M oflag=dsync
```
