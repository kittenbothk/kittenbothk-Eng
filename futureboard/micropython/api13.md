# Programming with MicroPython: I2C Device

## Import FutureBoard Library

Import the Library to make use of its functions.

    from future import *

## 13: I2C

## Initiate I2C Device

    i2c = I2C(0)  #Default I2C Port
    i2c = I2C(1, scl=Pin(5), sda=Pin(4), freq=400000) #Define own i2c pins

## I2C Scan Address

    i2c.scan()

## I2C Read

    i2c.readfrom(address,nbytes)

Returns data from the memory address.
Parameter nbytes define length of data.

## I2C Read into Buffer

    I2C.readfrom_into(addr, buf)

Reads data from the memory address.
The data sill be stored in parameter buf, which must be a bytearray.

## I2C Write

    i2c.writeto(address,buf)

Write data to a memory address.
The data in buf will be written to the device, buf must be a bytearray.

## I2C Write Vector

    i2c.writevto(address,vector)

Write a vector to a memory address.

## I2C Read from Memory

    I2C.readfrom_mem(address, memaddr, nbytes, *, addrsize=8)

Reads data from the I2C device address represented by address.
Reads data from the memory address represented by memaddr.
Parameter nbytes define length of data being read.
Parameter addrsize define the size of the memory.

## I2C Read from Memory into Buffer

    I2C.readfrom_mem_into(address, memaddr, buf, *, addrsize=8)

Reads data from the I2C device address represented by address.
Reads data from the memory address represented by memaddr.
The data sill be stored in parameter buf, which must be a bytearray.
Parameter addrsize define the size of the memory.

## I2 Write Buffer to Memory

    I2C.writeto_mem(address, memaddr, buf, *, addrsize=8)

Writes data to the I2C device address represented by address.
Writes data to the memory address represented by memaddr.
The data in buf will be written to the device, buf must be a bytearray or byte.
Parameter addrsize define the size of the memory.