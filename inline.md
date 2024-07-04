# Inline Assembly

One is able to include assembly instructions in C by using the `__asm__` directive.

This allows the programmer to do some cool stuff, like making raw syscalls without to `libc`.

My most recent use-case has been to write and test ARM assembly instructions by loading it onto a micro-controller, however.

Example:
```c
int 
main(void)
{
	__asm__(
		".thumb\n"
		"_start:\n"
		"movs	r3, #0x10000\n"
		"lsls	r3, r3, #15\n"
		"bmi	halt\n"
		"bmi	halt\n"
		"bmi	halt\n"
		"bmi	halt\n"
		"halt:\n"
		"bkpt\n"
	);
}
```
