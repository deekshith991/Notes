
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

## Video 8: Bit manipulation

***Race condition***: Difference between time a value is read and when it is written/updated.
Eg: When we read a value and try to set it to another value another part of program changes the read value.

- ***Atomic manipulation :*** Read-modify-write guaranteed to be done a one operation. Requires hardware support on the CPU.
- ***Bit Bitbanding***: specific 1MB area is mapped to a 32MB address space.

- use volatile so that compiler doesn't remove some pin value setting.

## Video 9: Embedded C programming | three ways to blink an LED
use [wokwi](https://wokwi.com) a simulator

#### Blinking LED
```c

#define LED D13

void setup(){
  pinMode(LED, OUTPUT);
}

void loop(){
  digitalWrite(LED, HIGH);
  delay(1000);
  digitalWrite(LED, LOW);
  delay(1000);
}
```

- Here D13 is the pin defined by STM32 SDK which is address of the pin 
- setup function will set all the GPIO pins to required mode here we are setting D13 to output mode.
- void loop run endlessly
- digitalWrite function is using to set the pin signal to high and low

## Video 10: General purpose IO in Microcontroller
- CPU can't access anything outside itself.
- when we need more data we interface Memory to the CPU.
- for reading and writing we send Address and data over a BUS with read or write enable signal.

- when a GPIO - set to output => CPU IS DRIVING the pin.
- when a GPIO - set to input  => External circuit drives the pin.
- if modes are set incorrectly it may cause it to short-circuit.

> [!INFO]
> So the CPU will always set a GPIO pin to input when it is initialized.

- Mode selection is done using a register.
- There are certain pins that can acts as a Analog/Digital pin.

> [!WARNING]
> For a floating pin we can't find the voltage. And there is high impedence.
> to avoid the undefined behaviour we use pull-down resistor to make it defined.


#### HAL code
```c

void initGPIO(){
  GIO_InitTypedef GPIO_Config;

  GPIO_Config.Mode = GPIO_MODE_OUTPUT_PP;
  GPIO_Config.Pull = GPIO_NOPULL;
  GPIO_Config.Speed = GPIO_SPEED_FREQ_HIGH;

  GPIO_Config.Pin = LED_PIN;

  SET_BIT(RCC-> IOPENR, RCC_IOPENR_GPIOAEN);
  HAL_GPIO_Init(LED_PORT, &GPIO_Config);
}
```

## Video 11: GPIO Usage


### Incase of output

- When a CPU is 1.8V and sensor is 5V it may cause problems.
- So we need to know about the connection buffer.

### Similar to current case

- If the CPU can only output 5mA and we need to run a 10mA load, the buffer may short-circuit.
- Similarly if the sensor sends in 40mA and CPU can only sink 10mA that will damage the port.

### If we want to drive a motor

- We can only send 5mA but motor needs 100mA.

If we connect directly:

1. Either the motor spins at 5% speed
2. Or the CPU gets short-circuited

- For this we use a switch where the CPU controls the ON/OFF.
- The switch will deliver the large amount of current.

- [Push Button](###pushuuu) are mechanical switches.
- [ESD Protection](#esd-protection) is required for the pins.
- Always check for ESD.

### Examples

- LED control — signaling, status
- Button inputs
- Driving relays
- Sensor interfacing
  - Analog / Digital
- Communication protocols
  - Bit Banging (software implementation)


### Push Button

It is a mechanical switch. When pressed and released it will bounce back.

- When debounced it cuts off the signal called **Debounce**.


### ESD Protection

ESD — Electro Static Discharge

This is the charge that builds up on a surface/body.

> Warning:
> Never touch the pins directly.

## Video 12: UART — Universal Asynchronous Receiver Transmitter

- Asynchronous — No shared clock.

![UART Data Packet Frame](Images/STM32-UART-Data-Packet-Frame.png)

- Always the idle state in UART is HIGH.
- First bit is LOW to say the data flow started.
- There is HIGH at the end to say that we are stopping data transfer.

### Parameters : 8N1 @ 9600

- 8 — number of data bits
- N — no parity bits
- 1 — one stop bit

9600 bits/second (Baud Rate)

### Disadvantages

- Speed lowers data rates
- Sensitive to baud-rate mismatch
- No shared clock — fails for clock drift
- Multi-master/multi-slave is not possible
- Frame overhead is significant
- Basic error detection, no correction
- Cable length decides the signal integrity
