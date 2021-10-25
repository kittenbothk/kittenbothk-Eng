# Ambient Light Sensor

![](../images/light2.png)

This is an ambient light sensor, it returns an analog value.

The range of return value is 0-1023, a higher value means a higher brightness reading.

## Specification

- Voltage: 3.3V~5V
- Type: Analog Sensor
- Interface: 3Pin PH2.0

## Wiring Diagram

    This is an analog module, it can only use P0-P2.(Remove the buzzer jumper when P0 is in use.)

### Robotbit Shield

Connect the sensor to Robotbit Shield's 3Pin port.

![](../images/light_wire2.png)

### Robotbit

Connect the sensor to Robotbit's pin and 3V pin.

![](../images/light_wire1.png)

## MakeCode Coding Tutorial

![](../PWmodules/images/mcbanner.png)

![](../../meowbit/images/acbanner.png)

### This module can be used with Microbit and Meowbit.

#### Reading the ambient light level

### Microbit:

![](../images/poten_code.png)

### Meowbit:

![](../images/poten_codeMeow.png)

## KittenBlock Coding Tutorial

![](../PWmodules/images/kbbanner.png)

### Load Robotbit Extension

![](../images/addRB.png)

#### Reading the ambient light level

![](../images/poten_codekb.png)

## Mu Editor Coding Tutorial

#### Reading the ambient light level

![](../images/poten_codemu.png)
