# Compiling and Running ARM Binaries on X86_64 (linux)

## Installing necessary tools
Download and install necessary tool chains, as well as qemu.

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
