
# SPI (serial peripheral interface)

![[spi-communication.png]]
this method is chain method. Here only 1 CS is needed as all slaves are connected is series.

In another method for every slave we need a dedicated CS pin

It is a communication protocol
It mainly has 4 lines but not mandatory depends


1. SCLK - serial clock (Master clock)
2. MOSI - Master out slave in (this sends data out of master)
3. MISO - Master in slave out (this recieves data from the slave)
4. CS/SS - chip select(Active low). it is used to set which slave we need to communicate.

In this communication protocol we don't need any Addressing for the slave as we are using CS.

CS we pull it to low to indicate we are online with slave.

MOSI & MISO sends data in serial order bits/second whether it sends MSB/LSB is sent based on the implementation.

## SPI modes


1. CPOL (clock polarity)
  - CPOL = 0 (NON-INVERTED): it means the data signal is low at ideal communication. data is sampled when signal is Active high.
  - CPOL = 1 (INVERTED): it means the data signal is high at ideal communication. data is sampled when signal is Active low.

2. CPHA (clock phase)
  - CPHA = 0 : we are sampling data at starting edge of data.
  - CPHA = 1 : we are sampling data at ending edge of data.


| Mode | CPOL | CPHA |
| ---- | ---- | ---- |
|   0  |   0  |   0  |
|   1  |   0  |   0  |
|   2  |   1  |   1  |
|   3  |   1  |   1  |



