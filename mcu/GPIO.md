
# GPIO

- for 8051 there are 3 ports with 7,8,8 pin

for each pin there is a register associated
- Data Direction register (controls the data direction)
  - 1 means output
  - 0 means input
- pin register (8 bit register)
  - this register hold 1 for the pins that are configured to input live state.
- port register
  - send data out it holds 0 for pins that output.


