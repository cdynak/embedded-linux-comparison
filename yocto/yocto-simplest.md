# yocto simplest example

## preparing system

### packages
```
$ sudo apt install gawk wget git-core diffstat unzip texinfo build-essential chrpath
$ wget http://commondatastorage.googleapis.com/git-repo-downloads/repo
$ chmod a+x repo
$ sudo mv repo /usr/local/bin/
```

### configure git
```
$ git config --global user.email "cdynak@ars-robotica.pl"
$ git config --global user.name "cezary dynak"
```

## fsl-community-bsp-platform (repo)
```
$ mkdir freescale-yocto
$ cd freescale-yocto
$ repo init -u https://github.com/Freescale/fsl-community-bsp-platform -b daisy
$ repo sync
```

## compilation (bitbake)
```
$ export MACHINE=wandboard-quad
$ source setup-environment build
$ bitbake fsl-image-multimedia
$ pv build/tmp/deploy/images/wandboard-quad/fsl-image-multimedia-wandboard-quad.sdcard
```
