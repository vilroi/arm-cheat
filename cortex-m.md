# ARM Cortex-M

The Micro-controller profile.
Optimized for power efficiency.

The M-profile **only supports Thumb mode**.

## Memory Model

The ARM cortex-M is a memory mapped architecture.

This is, the processor accesses various resources (both physical memory and its peripheral devices) share the same address space. 

The memory addresses in the 32bit address space is not necessarily backed by physical memory. Certain addresses are associated with the registers of I/O devices. 

Thus, if the processor accesses a certain address, it may be communicating with a peripheral, such as USART or the system clock, etc.

## Bus Protocols

### AHB: Advanced High Performance Bus Lite

Often considered the "main bus", since it is used for high speed communication between the processor, memory, and the peripherals.

Examples of devices using the AHB:

- DMA controller
- RCC
- GPIO Ports

### APB: Advanced peripheral bus

Used for peripherals that aren't as time critical.

Basically everything else that isn't connected to the AHB.

Examples:

- i2c
- spi 
- usart
