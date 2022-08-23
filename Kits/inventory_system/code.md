# Inventory System Sample Program

## RFID Chip Program

Use this program to check the ID of the RFID chips.

![](./images/rfid_code.png)

[Sample Program](https://makecode.microbit.org/_7mTPaUfz5FLd)

## MakerCloud Sample Program

![](./images/code_makercloud.png)

[Sample Program](https://makecode.microbit.org/_Ef8DP8gCThfX)

### Model Instructions

1. Fill in Wifi login information and MakerCloud MQTT topics
2. Fill in the corresponding RFID number for the product
3. Download the program and turn on the power, wait for the LED to completely light up
4. Press A to turn on the conveyor belt, B to turn if off
5. When the RFID Sensor detects a RFID chip, Micro:bit will display the ID and uploads the information to MakerCloud.

### MakerCloud Set Up Tutorial

Create new MQTT topic, create data types: item, koi, robotbit, armourbit.(For Reference)

![](./images/makercloud1.png)

Create chart for each data type.

![](./images/makercloud3.png)

Create dashboard, include the charts created.

![](./images/makercloud2.png)

## ObjectBlocks Sample Program

![](./images/code_objectblocks.png)

[Sample Program](https://makecode.microbit.org/_9UHYyzdWJM0E)

### Model Instructions

1. Fill in Wifi login information and ObjectBlocks MQTT topics
2. Fill in the corresponding RFID number for the product
3. Download the program and turn on the power, wait for the WifiBrick to connect with ObjectBlocks
4. Press A to turn on the conveyor belt, B to turn if off
5. When the RFID Sensor detects a RFID chip, Micro:bit will display the ID and uploads the information to ObjectBlocks

### ObjectBlocks Set Up Tutorial

Create new project.

![](./images/objectblocks1.png)

Create channels Robotbit, Armourbit, KOI, Item.(Webhook option must be selected)

![](./images/objectblocks2.png)

![](./images/objectblocks3.png)

![](./images/objectblocks4.png)

Create Dashboard.

![](./images/objectblocks5.png)

Create new tool to display the channel data.

![](./images/objectblocks6.png)

## ThingSpeak Sample Program

![](./images/code_thingspeak.png)

[Sample Program](https://makecode.microbit.org/_RU8DYRgbm1os)

### Model Instructions

1. Fill in Wifi login information and ThingSpeak MQTT topics
2. Fill in the corresponding RFID number for the product
3. Download the program and turn on the power, wait for the WifiBrick to connect with ThingSpeak
4. Press A to turn on the conveyor belt, B to turn if off
5. When the RFID Sensor detects a RFID chip, Micro:bit will display the ID and uploads the information to ThingSpeak


    Note: ThingSpeak does not allow string data, so Item Name and ID will not be supported

### ThingSpeak Set Up Tutorial

Create ThingSpeak Channel, create data field Robotbit, KOI, Armourbit, Item.

![](./images/thingspeak1.png)

Set the channel to public.

![](./images/thingspeak2.png)

Set up MQTT Device.

![](./images/thingspeak3.png)

Properly save the MQTT device credentials.

![](./images/thingspeak4.png)