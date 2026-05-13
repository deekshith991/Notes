# I2C - (Inter-Integrated Circuit)

1. SDA - Serial Data Line
2. SCL - Serial Clock

![[../Images/I2C-image.png]]

- Multi-master capable.
- Multiple slaves
- Addressing mechanism
- 2-wire
- 100kbps approx.

### Address frame
-  it has 7 bit 112 receivers
- And 10 bit mode 1008 receivers.

### operation
![[../Images/I2C-opration.png]]
- SDA , SCL  both are pulled up by the pull up resistors.
- In operation MASTER initiates transfer by pilling SDA down while SCL is initialized
- there is a start structure then a Address frame which tells us about mode
- 1 bit of read or write indication.
- 1 SCL wait period to receiver ACK/NACk
- then DATA packets with another ACK/NACk

### Advantages
- 2 wire.
- Multi-Master Multi-Slave
- ACK & NACk
- Well supported Addressing protocol
- Simple enough for Bit-Banging

### Disadvantages
- UART < Data rate of I2C < SPI
- 8 bit Data frame / overhead
- Hardware is more complex than SPI.
- Half-duplex mode only.

