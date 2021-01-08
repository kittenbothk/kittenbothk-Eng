# Water Sensor

![](./images/water2.png)

This is a water sensor that detects the presence of water and the water level and returns an analog value.

The range of the return value is 0-1023, a higher value means the water level is higher.

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

#### Reading the water level value

### Microbit:

![](./images/poten_code.png)

### Meowbit:

![](./images/poten_codeMeow.png)

## KittenBlock Coding Tutorial

![](./PWmodules/images/kbbanner.png)

### Load the Robotbit extension

![](./images/addRB.png)

#### Reading the water level value

![](./images/poten_codekb.png)

## Mu Editor Coding Tutorial

#### Reading the water level value

![](./images/poten_codemu.png)