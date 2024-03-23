# Indirect Branches

Indirect branches jump to an address that is not hard-coded in the binary.

Example:
```asm
    mov     r0, #0x100
    bx      r0
```

In the case of the above, the processor branches to address 0x100.

Branch instruction allow processors to compute addresses at run-time.

## BX: Branch and Exchange

