(MakeCode Coding)

# Makecode Coding and MakerCloud

![](../../functional_module/PWmodules/images/mcbanner.png)

## Foreword:

In this tutorial, you will learn how to use MakerCloud platfrom with a Wifibrick or KOI. A Robotbit will be used for demonstration.

## Step 1: Platform Preparation

Log in to MakerCloud and set up an IoT service.

Navigate to the mainpage and create a project.

    Or use ones that you created previously.

![](./iotimage/mc1.png)

You will be redirected to the main page of your IoT project. Select Create Topic.

![](./iotimage/mc2.png)

Create a MQTT topic.

![](./iotimage/mc3.png)

Navigate to the Internet of Things tab.

The topic name will be automatically generated, this topic name should remain secret as it is the key to access this topic.

![](./iotimage/mc4.png)

The IoT platform is now ready to be used for IoT operations.

## Step 2: Load the extension

We will load an extension so that we can communicate with MakerCloud's server.

Extension for Wifibrick: https://github.com/maxwong-scale/pxt-makercloud-V2

Extension for KOI: https://github.com/scaleinnotech/pxt-makercloud-koi

### [Loading Extensions](../../Makecode/powerBrickMC)

## Step 3: Coding

### 1: Connecting Wifibrick to MakerCloud

Blocks for initiating connection:

![](./iotimage/mc12.png)

As a Robotbit is used in this tutorial, we initiate the Wifibrick with Tx & Rx pins.

![](./iotimage/mc5.png)

Armourbit users can use ports to initialize.

![](./iotimage/mc6.png)

The Micro:bit will display a short animation when connecting to the Wifi.

![](./iotimage/mc16.gif)

The Micro:bit will display a short animation when connecting to the MQTT server.

![](./iotimage/mc17.gif)

### 2: Publishing to the Topic

Blocks for publishing:

![](./iotimage/mc13.png)

Let's publish a random number to our topic.

Copy and paste your topic name here.

![](./iotimage/mc7.png)

The data we sent will be shown in the real-time data feed.

![](./iotimage/mc10.png)

A chart will also be generated.

![](./iotimage/mc15.png)

We can manually publish data to a topic with this window.

![](./iotimage/mc11.png)

### 3: Subscribing to a Topic

Blocks for subscribing and reading data:

![](./iotimage/mc14.png)

In order to obtain data from a topic, a subscription is required.

In this example, let's subscribe to the same topic we publish data to.

![](./iotimage/mc8.png)

## Sample Program

### Sample Program for Wifibrick

![](./iotimage/mc9.png)

[Sample Code Link](https://makecode.microbit.org/_0yhUt94oTfTD)

### Sample Program for KOI

![](./iotimage/mc18.png)

[Sample Code Link](https://makecode.microbit.org/_2FfTJ1eMaKtV)

## Conclusion:

This concludes the basic usage of the MakerCloud platform with a Micro:bit, for more advanced usage, please refer to the official tutorials.

## Extension Version and Updates

There may be updates to extensions periodically, please refer to the following link to update/downgrade your extension.

[Makecode Extension Update](../../Makecode/makecode_extensionUpdate)