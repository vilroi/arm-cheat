# IT

The `if then` instruction is capable of creating a sequence of conditionals in the form of `if then else`.

The `IT` instruction does not affect the condition code flags.

Each subsequent `t`s and `e` adds an additional condition

Example:
```asm
800020e:       2b50            cmp     r3, #80 @ 0x50
8000210:       bf01            itttt   eq
8000212:       4a03            ldreq   r2, [pc, #12]   @ (8000220 <sv_call_handler+0x1c>)
8000214:       6953            ldreq   r3, [r2, #20]
8000216:       f083 0320       eoreq.w r3, r3, #32
800021a:       6153            streq   r3, [r2, #20]
800021c:       4770            bx      lr
800021e:       bf00            nop
```
