# Building Raspberry Pi Kernel

## Compiling The Raspberry Pi Kernel

Clone the git repo & start the vagrant box:

```
$ git clone https://github.com/stevenvo/build-rpi-kernel
$ cd build-rpi-kernel
$ vagrant up
```

Once the vagrant box is up, SSH in:

```
$ vagrant ssh
```

Now that you are connected to the VM, use `-h` for a list of options:

```
~$ sudo adabuild -h
usage: adabuild [options]
 This will build the Raspberry Pi Kernel.
 OPTIONS:
    -h        Show this message
    -r        The remote github kernel repo to clone in user/repo format
              Default: raspberrypi/linux
    -b        The git branch to use
              Default: Default git branch of repo
    -1        The config file to use when compiling for Raspi v1
              Default: arch/arm/configs/bcmrpi_defconfig
    -2        The config file to use when compiling for Raspi v2
              Default: arch/arm/configs/bcm2709_defconfig
```

Compile with default options:

```
~$ sudo adabuild
```

A `tar.gz` archive will be available in the current folder on the host machine
after the custom kernel has been built. Copy the archive to your Pi and extract the
contents. Installation instructions are included in the archive.

Disclaimer: Forked from https://github.com/adafruit/Adafruit-Pi-Kernel-o-Matic
