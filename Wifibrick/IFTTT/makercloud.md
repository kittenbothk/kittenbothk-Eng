# MakerCloud x IFTTT

We can upgrade our IoT projects by using IFTTT to achieve more functions such as emails or Telegram messages.

MakerCloud already has built-in support for easily incorporating IFTTT into your project.

## MakerCloud Official Guides

MakerCloud provides an official step-by-step tutorial on using IFTTT with MakerCloud.

### Step 1: Event Triggers

### [Event Triggers](https://learn.makercloud.io/en/latest/ch9_event_trigger/event_trigger/smartrack_ET/)

### Step 2: Event Triggers with IFTTT

### [Event Triggers with IFTTT](https://learn.makercloud.io/en/latest/ch9_event_trigger/ifttt/smartrack_IFTTT/)

## MakerCloud x IFTTT Guide

### The following content is written by KittenBot HK, please refer to official tutorial if any differences are found.

### Step 1: Event Triggers

Create a new project on MakerCloud.

![](./images/mc1.png)

Open the tab "Event Trigger".

![](./images/mc2.png)

Build the following applet.

![](./images/mc3.png)

For webhook event and webhook key, we can fill in random filler for now.

![](./images/mc4.png)

### Step 2: Set Up IFTTT

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

Go to "My services".

![](./images/mc19.png)

Select Webhooks.

![](./images/mc20.png)

Choose Documentation.

![](./images/mc21.png)

Copy the key.

![](./images/mc22.png)

Paste the key into the webhook key field in MakerCloud applet.

![](./images/mc23.png)

Enter the event name in the MakerCloud applet.

![](./images/mc24.png)

Save the applet.

![](./images/mc25.png)

Try publishing "hello" to your topic, you should receive an email after a few seconds.

![](./images/mc26.png)
