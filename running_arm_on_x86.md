# Compiling and Running ARM Binaries on X86_64 (linux)

## Installing the Necessary Tools
Install the arm toolchain and qemu.

On Arch linux:

```shell
$ sudo pacman -S arm-none-eabi-{gcc,binutils,gdb}
$ sudo pacman -S qemu-full
```

## Assembling and Linking Assembly files (static binaries)

```shell
$ arm-none-eabi-as test.S -o test.o
$ arm-none-eabi-ld -static test.o -o test
$ file test
test: ELF 32-bit LSB executable, ARM, EABI5 version 1 (SYSV), statically linked, not stripped
```

## Running the binary

```shell
$ qemu-arm ./test
```

## Debugging

Running the binary with qemu. 

The *-g* option specifies a port number for gdb to connect to.

```shell
$ qemu-arm -g 4444 file       
```

Starting GDB:

```shell
$ arm-none-eabi-gdb file
gef> gef-remote localhost 4444   # this assumes that gef is installed
```

## Resources
- [Running Arm Binaries on x86 with QEMU-User](https://azeria-labs.com/arm-on-x86-qemu-user/)
