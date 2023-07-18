# OpenTTD on Raspberry Pi

Resources for running OpenTTD on the Raspberry Pi

## Builds

Here's a list of binaries I've built for OpenTTD:

- OpenTTD 13.3 64-bit, Built 18/07/2023 with a Raspberry Pi 4: [Download](https://github.com/Owez/openttdrpi/blob/master/binaries/openttd-rpi4-64bit-v13-3.zip) 

## Compiling

A short guide on how to compile & run a modern OpenTTD binary on a Raspberry Pi that'll work for newer generations (3/4/etc). After reading this, you might want to look at the resources for [dedicated servers](https://wiki.openttd.org/en/Manual/Dedicated%20server)!

First, download the zipped source files from the [downloads page](https://www.openttd.org/downloads/openttd-releases/latest); this unzipped directory will be referred to as the *source directory*. Once you have them unzipped, install the following compilation dependencies:

```shell
sudo apt-get update
sudo apt-get install build-essential pkg-config libsdl1.2-dev subversion patch zlib1g-dev liblzo2-dev liblzma-dev libfontconfig-dev libicu-dev
sudo apt-get install cmake
```

One or two of these dependencies probably aren't needed but it's fine. Once you have these dependencies installed, you should be able to run the following commands inside of the unzipped source directory:

```shell
mkdir build
cd build
cmake .. -DCMAKE_BUILD_TYPE=RelWithDebInfo
make -jobs=4
```

Linking takes forever but you should now have a compiled release version of OpenTTD to use on your Raspberry Pi :)
