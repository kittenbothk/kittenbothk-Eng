# Analog Flame Sensor

![](../images/fire2.png)

This module can detect fire, it returns an analog value.

The range of the return value is 0-1023, a higher value means the sensor is closer to fire.

## Specification

- Voltage: 3.3V~5V
- Type: Analog Sensor
- Interface: 3Pin PH2.0

## Wiring Diagram

    This is an analog module, it can only use P0-P2.(Remove the buzzer jumper when P0 is in use.)

### Robotbit Shield

Connect the sensor to Robotbit Shield's 3Pin port.

![](../images/fire_wire2.png)

### Robotbit

Connect the sensor to Robotbit's pin and 3V pin.

![](../images/fire_wire1.png)

## MakeCode Coding Tutorial

![](../PWmodules/images/mcbanner.png)

![](../../meowbit/images/acbanner.png)

### This module can be used with Microbit and Meowbit.

#### Reading the flame value

### Microbit:

![](../images/poten_code.png)

### Meowbit:

![](../images/poten_codeMeow.png)

## KittenBlock Coding Tutorial 

![](../PWmodules/images/kbbanner.png)

### Load the Robotbit extension

![](../images/addRB.png)

#### Reading the flame value

![](../images/poten_codekb.png)

## Mu Editor Coding Tutorial

#### Reading the flame value

![](../images/poten_codemu.png)