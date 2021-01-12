(IoT Platform Introduction)

# ThingSpeak

## Introduction

[ThingSpeak](https://thingspeak.com/)

ThingSpeak is a IoT analysis platform managed by Mathworks, through the internet, data can be collected and uploaded to ThingSpeak using Rest API or MQTT protocol, the data is analyzed and represented as real time graphs.

Of course, ThingSpeak can be used to exchange data by uploading data from device A and then downloading that data from device B.

![](./iotimage/iot-01-01.png)

ThingSpeak is a popular platform for both beginners and professionals. ThingSpeak is available as a free version or as a paid version, the free version is a great platform for beginners.

[ThingSpeak Licensing](https://thingspeak.com/pages/license_faq)

## Account Registration

An account is needed for using ThingSpeak.
 
We can create a free account here.

![](./iotimage/iot-02-01.png) 

Select "Create Acconut" or click "Sign In" if you already have an account.   

 ![](./iotimage/iot-03-01.png)

Fill in the information and click "Continue".

 ![](./iotimage/iot-04-01.png)

Tick this option.

 ![](./iotimage/iot-05-01.png)

Activate the account by following the given steps.

Do not close this page.

 ![](./iotimage/iot-06-01.png)

Verify your email to continue.

 ![](./iotimage/iot-07-01.png)

 ![](./iotimage/iot-08.png)

Go back to the page and click "Continue".

 ![](./iotimage/iot-09-01.png)

Create a password.

 ![](./iotimage/iot-10-01.png)

After that, the sign up process is finished.

 ![](./iotimage/iot-11-01.png)

## Using the ThingSpeak platform

This is the main page after signing in to the platform. For beginners, we just need to know about **Channels** and **Profile**.

![](./iotimage/iot-12.png)

Their functions will be explained in the sections below.

In the **Support** page, documentation and technical support can be found.

## Set up a channel

You can create your own channels for uploading and downloading data, free accounts can create up to 4 channels.

Click New Channel

 ![](./iotimage/iot-14-01.png)

There are some information we need to provide when creating a channel.

We need to understand "Fields" first.

Fields are the attributes or the kinds of data that you are collecting. For example when we are monitoring the climate of a location, we may have fields including temperature, precipitation, humidity.

Fields can help us analyze data by representing our findings in a graph.

**Example**: Brightness, temperature, humidity, ambient noise are the fields we need when collecting environmental data of a classroom.

 ![](./iotimage/iot-15-01.png)

**Attention:** Each channel is limited to a maximum of 8 fields.

We can save our channel after finishing.

[More channel settings:](https://ww2.mathworks.cn/help/thingspeak/channel-settings.html)

## Channels

When we enter a channel, we are greeted with this page.

![](./iotimage/iot-17.png)

We can see the details of our channel.

![](./iotimage/iot-18.png)

1. An unique Channel ID used to access this channel.

2. Accessibility. Channels are defaulted to be Private, meaning only you can access this channel.
    - Changing it to Public would allow others to access this channel.
    - Free accounts are allowed up to 3 Public Channels.

   ![](./iotimage/iot-19.png)

3. Our data will be shown in these charts.

   e.g. Field 1 Chart = Brightness

    ![](./iotimage/iot-21-01.png)

The channel can be edited in the Channe Settings page.

 ![](./iotimage/iot-22-01.png) 

We can return to this channel page from other pages with the following steps.

 ![](./iotimage/iot-20-01.png)

## Publish & Subscribe

**Publish** and **Subscribe** are important concepts in IoT applications. 

In a nutshell, Publish means uploading data to the platform, while Subscribe is to download the data from the platform.

 ![](./iotimage/iot-26-01.png)

#### Publish

Publish data to a channel requires the **Write API Key**. This information should be kept a secret.

Our Write API Key for this channel can be found here.

 ![](./iotimage/iot-27-01.png)

 ![](./iotimage/iot-28-01.png)

#### Subscribe

Subscribing to a channel requires the **MQTT API Key** of the channel owner's account. This information should be kept a secret.

Go to My Profile.

 ![](./iotimage/iot-29-01.png)

The MQTT API Key is found here.

 ![](./iotimage/iot-30-1.png)

ThingSpeak is powered by MathWorks and full features can be accessed with a paid account. Enthusiasts can know more about these powerful features by reading the documentation.