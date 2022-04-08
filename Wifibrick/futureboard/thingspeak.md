# FutureBoard and ThingSpeak 

ThingSpeak is free to use, however its settings may be difficult for beginners. This tutorial is suitable for complete beginners to start using ThingSpeak with FutureBoard.

## Registering a ThingSpeak Account

Follow the instructions to register for a ThingSpeak account.

[ThingSpeak Introduction](../IoTPlatform/Thinkspeak.md)

## Setting Up ThingSpeak Platform

### Create a new Channel

Create a new channel.

![](./images/1.png)

Choose a name for your channel.

![](./images/2.png)

Other fields can be ignored, click Save Channel.

![](./images/3.png)

Open the Sharing tab.

![](./images/4.png)

Set the sharing settings to "Share channel view with everyone".

![](./images/5.png)

The Access with change to "Public".

![](./images/6.png)

### Add a new device

Open the Devices menu, select MQTT.

![](../futureboard/images/7.png)

Add a new device.

![](../futureboard/images/8.png)

![](../futureboard/images/9.png)

Select the channels accessible by this device and click Add Channel.

![](../futureboard/images/10.png)

Click Add Device.

![](../futureboard/images/11.png)

IMPORTANT! These MQTT Credentials are used for connecting to ThingSpeak! Please save or download the credentials as they can't be seen after closing this page.

![](../futureboard/images/12.png)

![](../futureboard/images/13.png)

## KittenBlock Coding

KittenBlock is recommending for beginners.

### Connecting to ThingSpeak

Build the following program with the following parameters to connect to ThingSpeak.

- MQTT Host: mqtt3.thingspeak.com
- ID: ThingSpeak Device ID
- Username: ThingSpeak Device ClientID
- Password: ThingSpeak Device Password

![](./images/14.png)

### Publishing to ThingSpeak Channel

We need the Channel ID for publishing. The channel ID is displayed on the Channel page as a 7-digit number.

![](./images/15.png)

Build the following program to publish a data to ThingSpeak:

- MQTT Topic: channels/[Channel ID]/publish
- Message: field[field No.]=[Numeric Data]

![](./images/16.png)

On the ThingSpeak page, you can see the published data.

![](./images/17.png)

### Subscribing to ThingSpeak Channel

We can read the channel data by subscribing to the channel.

- MQTT Topic: channels/[Channel ID]/subscribe/fields/field[field No.]

Press A to publish a message to the channel, FutureBoard will display the data received.

![](./images/18.png)