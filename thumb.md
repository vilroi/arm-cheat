## Thumb Instruction Set

The thumb instruction set is a "subset" of the ARM instruction set.

While ARM uses 4 bytes for each instruction, thumb only uses 2 bytes.

The reduction of instruction size leads to less memory usage, but has the disadvantage of not being able to use all of the instructions.

(In reality there are probably many other pros and cons. I will research them some time in the future.)

## Comparing ARM and Thumb Instructions

Here is a comparison of the disassembly of the same code assembled with ARM and Thumb respectively.

### "ARM" Assembly 

```assembly
// arm-exit.S
.global _start

_start:
    mov r0, #32
    mov r7, #1
    svc $0
```

### "Thumb" Assembly

For the thumb variant, the *.thumb* and *.thumb_func* macro is added.

```assembly
// thumb-exit.S
.global _start
.thumb

.thumb_func
_start:
    mov r0, #32
    mov r7, #1
    svc $0
```


### Disassembly of ARM Binary

```shell
00008000 <_start>:
    8000:       e3a00020        mov     r0, #32         <--- 4 byte instructions
    8004:       e3a07001        mov     r7, #1
    8008:       ef000000        svc     0x00000000
```

### Disassembly of Thumb Binary
```shell
00008000 <_start>:
    8000:       2020            movs    r0, #32         <--- 2 byte instructions
    8002:       2701            movs    r7, #1
    8004:       df00            svc     0
```
