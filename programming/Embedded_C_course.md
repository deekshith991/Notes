
# Embedded C course

## Need to know
!Bitbanding

## Keywords
1. SoC - System on Chip
2. ELF - Executable and Linkable Format

## Video 3

- **Instruction set :** how does a code is understood by the hardware.

Microcontroller Families

1. AVR
  - Atmel: founder of AVR
    - Flash based.
    - 8-bit, extended later.

  - Adruino:
    - common boards.

2. PIC
  - From 1976 - Microchip Technology Inc.
  - Low cost.
  - used EEROM (Electronically Erasable Readonly Memory). To erase used UV light.

3. MSP 430
  - Texas Instruments.
  - Ultra Low Power Applications.
    - 0.1uA RAM retention.
    - 0.7uA RTClock operation.
  - Easy to use USB-power/debug.

4. ESP32
  - Espressif systems.
  - Low-cost, Many pheripherals, Bluetooth and wifi.
  - Tensilica XTensa ISA (Cadence).

> [!NOTE]
> This is main target base.
5. ARM
  - Advanced RISC Machine (originally "Acorn RISC Machine").
  - **RISC:** Reduced Instruction Set Computing.
  Cortex series Variants of 32-bit
    - **A - Application series :**
      - Memory management, full OS support.
      - used for Laptops and phones.
    - **R - Real-time :**
      - integrated memory with error correction.
    - **M - Microcontroller :**
      - No memory management, standalone only.
      - Low-power, embedded applications focus.

## Video 5
Basics of Embedded C - contains C topics.

- stdint.h for bit control size assignment of datatypes.
- Stack and Heap

- stack -> given to function
- Heap  -> Longer-lived and Global (Needs careful allocation).

## Video 6

##### Efficiency
- Resource: memory,CPU,IO bandwidth.
- speed: types of CPU Instruction.
- Power: Sleep states, power modes.

##### steps for Efficiency
- Don't use Standard INT use stdint library.
- Don't use redundant Global Variables in. Try to use dynamic local variables.
- Reduce the DYNAMIC Alloc and Dealloc.

##### Best practices
- Avoid Floating point computation.
- try using -O2 for speed improvement in compiling.
- try using -Os for producing small binary.

## Video 7: Memory management
***Static memory allocation***: We need to allocate the memory before the binary starts running.
- Avoid's fragmentation.
- used mainly at memory safety devices.
- No complex data structures.

And some more info on Dynamic memory allocation.



