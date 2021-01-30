# Wifibrick

Wifibrick (HKBM8012O)

## Introduction

Wifibrick is an expansion module for Kittenbot's Powerbrick.

As the name suggests, this module provides a method for Micro:bit to connect to the internet, allowing it to connect to various IoT platforms such as ThingSpeak, MakerCloud or OneNet.

 ![](./introimage/wifi-01-1.png)

Appearance-wise, it is largely identical to the Temperature and Humidity Module, with the exception of a logo printed on the Wifibrick.

 ![](./introimage/wifi-02.png)

## Specifications	

- Voltage: 3.3-5V  
- Current: ~65mA
- Dimensions: 56 (L) x 25 (W) x 20 (H)
- Connector: 4Pin PH2.0
- Supports STA/AP/STA+AP
- Supports Smart Config

 ![](./introimage/wifi-05-1.png)

## Special Features	

- Micro:bit compatible Wifi modules are rare in the market, therefore Kittenbot has developed the firmware and MakeCode extension.

- With a built-in indicator LED, connection status can be read.

- The PH2.0 Cable prevents incorrect connection.

     ![](./introimage/wifi-04-1.png)

- Lego Pin connectors are installed into the sides and the back of the module, making it very easy to integrate into different models.

     ![](./introimage/wifi-09-1.png)

## Pin out Explaination

On the back of the WifiBrick, the pin out is labelled as G, V, A, B.

 ![](./introimage/wifi-22-1.png)

The functions of the 4 pins are as follows:

 ![](./introimage/wifi-23-1.png)

Tx = Transmit(*Tx*) Data

Rx = Receive(*Rx*) Data

## Connecting the module

 ![](./introimage/wifi-06-1.png)

There are numerous ways to connect the Wifibrick to a Micro:bit, it is recommended to use Kittenbot's expansion boards.

Details are as follows:

### Armourbit

Armourbit is an expansion box designed for Micro:bit. Wifibrick can be connected to Armourbit using a 4Pin cable.

 ![](./introimage/wifi-07-1.png)

[Armourbit Details](../functional_module/PWmodules/Armourbit)

The 2 ends of the cable are both PH2.0.

 ![](./introimage/wifi-08-1.png)

Connect Wifibrick to the Port 1(Requires turning off the buzzer) to Port 4 of the Armourbit using the cable.

In this figure, Port 2 is used, this corresponds to P1 and P12 of the Micro:bit.

![](./introimage/wifi-13-1.png)

Wiring Details:

![](./introimage/wifi-12-1.png)

### Robotbit

Robotbit is a popular Micro:bit expansion board by Kittenbot, it supports a wide variety of modules including Wifibrick.

[Robotbit Details](../Microbit_eboard/Robotbit/Robotbitfull)

Using a PH2.0 to Dupont Cable, connect the Dupont pins to G, V and 2 signal pins on the Robotbit.

 ![](./introimage/wifi-16-1.png)

In this figure, Pin 1 and Pin 2 is used.

 ![](./introimage/wifi-20-1.png)

 ![](./introimage/wifi-19-1.png)

Wiring Details:

 ![](./introimage/wifi-18-1.png)

### IoBit

IoBit is a basic Micro:bit extension board by Kittenbot, Wifibrick is supported on this board.

The connection method is identical to Robotbit. Using a PH2.0 to Dupont Cable, connect the Dupont pins to G, V and 2 signal pins on the IoBit.

In this figure, Pin 1 and Pin 2 is used.

 ![](./introimage/wifi-21-1.png)
