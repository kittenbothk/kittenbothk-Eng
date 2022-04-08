# ThingSpeak x IFTTT

ThingSpeak can also be configured to use IFTTT.

## ThingSpeak Official Tutorial

ThingSpeak provides an official tutorial.

### [ThingSpeak Official Tutorial](https://uk.mathworks.com/help/thingspeak/use-ifttt-to-send-text-message-notification.html?requestedDomain=)

## ThingSpeak x IFTTT

### The following content is written by KittenBot HK, please refer to official tutorial if any differences are found.

### Set Up IFTTT

Register and log in to an IFTTT account.

![](./images/mc5.png)

Create a new applet.

![](./images/mc6.png)

![](./images/mc7.png)

Search for webhooks in the "If this" section.

![](./images/mc8.png)

Select "Receive A Web Request".

![](./images/mc9.png)

Press connect if prompted.

![](./images/mc10.png)

Enter an event name.

![](./images/mc11.png)

Move on to "Then That" section.

![](./images/mc12.png)

In this tutorial ,we will use IFTTT to send an email. But there are many other applications supported too, please feel free to explore on your own.

![](./images/mc13.png)

Select Send Me an Email.

![](./images/mc14.png)

We have to activate this service for the first time when using this service.

![](./images/mc15.png)

Follow the instructions to activate email service.

![](./images/MC16.png)

You can modify the email contents, but we will use default settings for this tutorial.

![](./images/mc17.png)

Press Continue.

![](./images/mc18.png)

### Set up ThingSpeak

Navigate to the Apps tab.

![](./images/ts1.png)

Select ThingHTTP in actions.

![](./images/ts2.png)

Create a new ThingHTTP.

![](./images/ts3.png)

Enter a name for this action.

![](./images/ts4.png)

Switch to IFTTT page.

Go to "My services".

![](./images/mc19.png)

Select Webhooks.

![](./images/mc20.png)

Choose Documentation.

![](./images/mc21.png)

Enter an action name.

![](./images/ts5.png)

![](./images/ts6.png)

Copy this link and paste into the URL field.

![](./images/ts7.png)

Save the ThingHTTP.

![](./images/TS8.png)

Choose React from the apps.

![](./images/ts9.png)

Create a new React.

![](./images/ts10.png)

Enter the conditions for this trigger and select the ThingHTTP you want, tick "Run action each time condition is met" if you want to trigger the action everytime the condition is met.

![](./images/ts11.png)

Try publishing data to your ThingSpeak channel, you should receive an email if the conditions are met.

![](./images/mc26.png)