# Instructions Related to Bit Operations

## LSLS
Logical shift left.
Depending on the resulting value, it modifies the *N* or *Z* flag as a side-effect.
Example:
```asm
    mov     r3, #0x10000
    lsls    r3, r3, #15
```

In the above, the *N* bit is set, indicating that bit 16 is set within a 32bit register.
