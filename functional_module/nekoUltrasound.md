# NekoUltraSound Sensor

NekoUltraSound Sensor (HKBM8014A)

![](./images/ultrasound2.png)

This is an ultra sound distance sensor.

## Specification

- Voltage: 5V
- Working Tempeature: -25 ~ +80°C
- Signal Span: 30° Arc
- Detection Range: 5~300cm (Error<1cm)
- Interface: 4Pin Dupont Cable

## Wiring Diagram

The Ultra Sound sensor must connect to 5V.

![](./images/ultraSound1.jpg)

### Ultra Sound Sensor V2

Connect the A(RGB LED) and D(Sensor) pin of Ultra Sound Sensor V2.

![](./images/ultraSoundv2_wire.png)

### Ultra Sound Sensor V1

Connect the Ultr pin of Ultra Sound Sensor V1.

![](./images/ultraSoundv1_wire.png)

## MakeCode Coding Tutorial

![](./PWmodules/images/mcbanner.png)

![](../meowbit/images/acbanner.png)

### This module can be used with Microbit and Meowbit.

### Microbit:

### Load Robotbit Extension: https://github.com/KittenBot/pxt-robotbit

### [How to load extension?](../Makecode/powerBrickMC)

### Ultra Sound Sensor blocks:

![](./images/ultraSound_blocks.png)

#### Reading the distance:

![](./images/ultraSound_code1.png)

[Sample Code Link](https://makecode.microbit.org/_Lt021WgXuWfz)

### Controlling the RGB LED(only for V2)：

![](./images/ultraSound_code2.png)

[Sample Code Link](https://makecode.microbit.org/_J9R5xhCwgJqH)

### Demo Case:

![](./images/ultraSound_code3.png)

[Sample Code Link](https://makecode.microbit.org/_5vf48tf6xdVc)

### Meowbit:

### Load Robotbit Extension: https://github.com/KittenBot/meow-robotbit

### [How to load extension?](../Makecode/powerBrickMC)

### Load NeoPixel Extension:

![](./images/neopixel.png)

### Ultra Sound Sensor Blocks:

![](./images/ultraSound_blocks.png)

#### Reading the distance:

![](./images/ultrasound_codeMeow1.png)

[Sample Code Link](https://makecode.com/_fC6XoUHHR79p)

### Controlling the RGB LED(only for V2)：

![](./images/ultrasound_codeMeow2.png)

[Sample Code Link](https://makecode.com/_hs3LykMzV78o)

## Extension Version and Updates

There may be updates to extensions periodically, please refer to the following link to update/downgrade your extension.

[Makecode Extension Update](../Makecode/makecode_extensionUpdate)


## KittenBlock Coding Tutorial

![](./PWmodules/images/kbbanner.png)

### Load Robotbit extension

![](./images/addRB.png)

#### Reading the distance:

![](./images/ultraSound_code4.png)

### Controlling the RGB LED(only for V2)：

![](./images/ultraSound_code5.png)

## Mu Editor Coding Tutorial

#### Reading the distance:

![](./images/ultraSound_code6.png)

    The logic works by writing a broadcast signal then measuring the time taken for the signal to bounce back to the sensor, multiplying this time by the speed of sound gives us the distance.
