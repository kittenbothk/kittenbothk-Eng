# Potentialmeter

![](./images/poten2.png)

This is a potentialmeter that reads the rotation degree, it returns an analog value.

The range of the return value is 0-1023, a higher value means the rotation degree is bigger.

## Specification

- Voltagw: 3.3V~5V
- Type: Analog Module
- Interface: 3Pin PH2.0

## Wiring Diagram

    This is an analog module, it can only use P0-P2.(Remove the buzzer jumper when P0 is in use.)

### Robotbit Shield

Connect the sensor to Robotbit Shield's 3Pin port.

![](./images/poten_wire2.png)

### Robotbit

Connect the sensor to Robotbit's pin and 3V pin.

![](./images/poten_wire1.png)

## MakeCode Coding Tutorial

![](./PWmodules/images/mcbanner.png)

![](../meowbit/images/acbanner.png)

### This module can be used with Microbit and Meowbit.

#### Reading the sensor value

### Microbit:

![](./images/poten_code.png)

### Meowbit:

![](./images/poten_codeMeow.png)

## KittenBlock Coding Tutorial

![](./PWmodules/images/kbbanner.png)

### Load the Robotbit extension

![](./images/addRB.png)

#### Reading the sensor value

![](./images/poten_codekb.png)

## Mu Editor Coding Tutorial

#### Reading the sensor value

![](./images/poten_codemu.png)