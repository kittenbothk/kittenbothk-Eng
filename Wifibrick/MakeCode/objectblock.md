# Makecode Coding and ObjectBlocks

## Foreword

The following tutorial is for WifiBrick and Robotbit, for KOI users, some programs may need adjustments to work on KOI.

## 1: Setting Up ObjectBlocks

Create an account on ObjectBlocks.

[ObjectBlocks](https://www.objectblocks.cc/)

Log in and create a new project.

![](./iotimage/object1.png)

![](./iotimage/object2.png)

Select Channels from the menu.

![](./iotimage/object3.png)

Add a new channel.

![](./iotimage/object4.png)

Specify the type to be either text or numeric.

Remember to choose YES for the webhook option.

![](./iotimage/object5.png)

![](./iotimage/object6.png)

The webhook option contains credentials for accessing your channel, please keep confidential.

![](./iotimage/object7.png)

Publishing and subscribing to the channels requires credentials.

![](./iotimage/object8.png)

In order to visualize the data on ObjectBlocks, we need to create a dashboard.
Add a new dashboard via the menu.

![](./iotimage/object9.png)

![](./iotimage/object10.png)

Add a tool.

![](./iotimage/object11.png)

Many kinds of representations are available, for this tutorial, text will be used.

![](./iotimage/object12.png)

Select the channel we've just created.

![](./iotimage/object13.png)

## 2. MakeCode Coding

![](../../functional_module/PWmodules/images/mcbanner.png)

### Import WifiBrick Extension

Search for Kittenbot and import KittenWifi.

![](./iotimage/object14.png)

    For KOI user, import KOI.

### 1: Connecting to ObjectBlocks platform.

Fill in the authentication credentials for ObjectBlocks.

MQTT Host: hub2.objectblocks.cc
Node: Does not matter
Username: Your username(Host)
Password: Your password(Pass)

![](./iotimage/object15.png)

### 2: Publishing to ObjectBlocks

Copy and paste your ObjectBlocks topic into the publishing block.

![](./iotimage/object16.png)

### 3: Subscribing to ObjectBlocks

Copy and paste your ObjectBlocks topic into the subscribing block.

![](./iotimage/object19.png)

### 4. Final Program

Press A to publish a random number to ObjectBlocks, the number is shown on the Dashboard as well as the Micro:bit.

![](./iotimage/object21.png)

### Sample Program

![](./iotimage/object20.png)

[Sample Program](https://makecode.microbit.org/_3Picjj2KRChw)
