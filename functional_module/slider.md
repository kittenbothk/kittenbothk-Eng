# Slider Potentialmeter

![](./images/slide1.png)

This is a potentialmeter with a slider, it reads the position of the slider and returns an analog value

The range of the return value is 0-1023, a higher value means the position is higher.

## Specification

- Voltagw: 3.3V~5V
- Type: Analog Module
- Interface: 3Pin Dupont Cable

## Wiring Diagram

    This is an analog module, it can only use P0-P2.(Remove the buzzer jumper when P0 is in use.)
    
Connect the sensor to Robotbit's pin and 3V pin.

![](./images/slider_wire.png)

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