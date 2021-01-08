# Infra Red Tracker Sensor

![](./images/infrared1.png)

This is an infra red tracker sensor, it can detect when an object is close, it returns an analog value.

The range of the return value is 0-1023, a higher value means the object is closer to the sensor.

## Specifications

- Voltage: 3.3V~5V
- Type: Analog Module
- Interface: 3Pin Dupont Cable
- Detection Distance: 10-60mm

## Wiring Diagram

    This is an analog module, it can only use P0-P2.(Remove the buzzer jumper when P0 is in use.)
    
Connect the sensor to Robotbit's pin and 3V pin.

![](./images/infrared_wire.png)

## Adjust Sensitivity

The sensor's sensitivity can be adjusted via this potentialmeter. Use a screwdriver to turn.(Turn left to increase, turn right to decrease)

![](./images/infrared2.png)

## MakeCode Coding Tutorial 

![](./PWmodules/images/mcbanner.png)

![](../meowbit/images/acbanner.png)

### This module can be used with Microbit and Meowbit.

#### Read the IR sensor value

### Microbit:

![](./images/poten_code.png)

### Meowbit:

![](./images/poten_codeMeow.png)

## KittenBlock Coding Tutorial 

![](./PWmodules/images/kbbanner.png)

### Load the Robotbit extension

![](./images/addRB.png)

#### Read the IR sensor value

![](./images/poten_codekb.png)

## Mu Editor Coding Tutorial 

#### Read the IR sensor value

![](./images/poten_codemu.png)