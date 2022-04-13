# IoT Platform x MIT AI2

IoT use cases are usually paired with a mobile application, by using MIT AI2, we can easily build an app for using IoT use cases.

## MakerCloud x MIT AI2

MakerCloud has an official extension for using their platform with MIT AI2, please refer to their official documentation for details.

[MakerCloud Official Documentation](https://learn.makercloud.io/zh_TW/latest/ch4_connect/ai2/connect_ai2/)

## Other IoT Platform x MIT AI2

### Most platforms supporting MQTT will support MIT AI2, ThingSpeak is used as an example in this article.

Download a 3rd party MQTT extension for AI2.

[Download Extension](https://ullisroboterseite.de/android-AI2-PahoMQTT-en.html)

![](./images/1.png)

Download the file from Download section.

![](./images/2.png)

Extract the aix file.

![](./images/3.png)

![](./images/4.png)

Go to MIT AI2, open a new project.

[MIT AppInventor 2](http://appinventor.mit.edu/)

![](./images/5.png)

Find "Import Extension" from the left hand side menu.

![](./images/6.png)

Upload the aix file.

![](./images/7.png)

![](./images/8.png)

Drag the component into the screen.

![](./images/9.png)

In the properties of the MQTT component, enter the MQTT host in the Broker field. 

Fill in other parameters according to the requirements of your IoT platform.

For ThingSpeak, fill in mqtt.thingspeak.com for broker and your ThingSpeak clientID for clientID.

![](./images/10.png)

Enter UserName and UserPassword if required, for ThingSpeak, enter the user name and password here.

![](./images/11.png)

## Connecting to your chosen platform

Build the following program to test if you can connect to the IoT platform.

![](./images/12.png)

![](./images/13.png)

After pressing the button, the text should change to "true", this indicates a connection to the IoT platform has been established.

![](./images/14.jpg)

## Publishing messages on AI2

Try sending a random number to the platform.

![](./images/15.png)

![](./images/16.png)

![](./images/17.png)

Enter the topic name, ThingSpeak is used as the example in this article.

![](./images/18.png)

Attach a string element to the message parameter.

![](./images/19.png)

For ThingSpeak, join the 2 strings containing the field number and the data.

![](./images/20.png)

Try the program, you should be able to see the data on ThingSpeak.

![](./images/21.png)

## Subscribing to MQTT on AI2

We can also subscribe and listen to MQTT data.

Build the following program to read MQTT data.

![](./images/22.png)

![](./images/23.png)

Use the following block to trigger an action after a message is received.

![](./images/24.png)

Try the program, you should be able to see the data on ThingSpeak and on your app.

![](./images/25.png)

![](./images/26.jpg)

## Download Sample Program

The above program is available to download.

[AI2 Sample Program Download](https://drive.google.com/file/d/1g0Bf8zQGRk6PEBNDGzEWxrBTcfsoehhQ/view?usp=sharing)