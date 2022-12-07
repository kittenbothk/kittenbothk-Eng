# Inventory System Futureboard Sample Program

## RFID Sample Program

Check the ID of the RFID chips with this program.

### KittenBlock

![](./images/rfid_futureboard.png)

[Sample Program](https://github.com/kittenbothk/kittenbothk/blob/master/Kits/inventory_system/images/rfid_futureboard.sb3)

### Python

    #/bin/python

    from time import sleep
    from future import *
    from sugar import *
    def probeCallback():
      global x
    
      screen.fill((0, 0, 0))
      screen.text(str("Place RFID Tag"),5,10,1,(0, 119, 255))
      screen.text(str(RFID().uuid()),5,30,2,(0, 119, 255))
      screen.refresh()
    
    x = 0
    
    screen.sync = 0
    
    screen.fill((0, 0, 0))
    
    screen.text(str("Place RFID Tag"),5,10,1,(0, 119, 255))
    
    screen.refresh()
    
    sleep(1)
    
    while True:
      RFID().probe(probeCallback if 'probeCallback' in dir() else None)
      sleep(2)

[Sample Program](https://github.com/kittenbothk/kittenbothk/blob/master/Kits/inventory_system/images/rfid_futureboard.py)


## MakerCloud Sample Program

### KittenBlock

![](./images/code_makercloud_futureboard.png)

[Sample Program](https://github.com/kittenbothk/kittenbothk/blob/master/Kits/inventory_system/images/code_makercloud_futureboard.sb3)

### Python
    #/bin/python
    
    from time import sleep
    from future import *
    from sugar import *
    import mqttsimple
    import robotbit
    def probeCallback():
      global id,robotbit_count,koi_count,armourbit_count,msg
      id = RFID().uuid()
      if id in robotbit_tags:
        msg = "Robotbit."
        robotbit_count += 1
        mqtt.publish("/topic", str("_dn=future,_dsn=future,robotbit=")+str(robotbit_count))
      else:
        if id in koi_tags:
          msg = "KOI."
          koi_count += 1
          mqtt.publish("/topic", str("_dn=future,_dsn=future,koi=")+str(koi_count))
        else:
          if id in armourbit_tags:
            msg = "ArmourBit."
            armourbit_count += 1
            mqtt.publish("/topic", str("_dn=future,_dsn=future,armourbit=")+str(armourbit_count))
      sleep(1)
      screen.fill((0, 0, 0))
      screen.text(str("Place RFID Tag"),5,10,1,(0, 119, 255))
      screen.text(str(id),5,30,2,(0, 119, 255))
      screen.refresh()
      mqtt.publish("/topic", str(msg)+str(id))

    id = 0
    robotbit_count = 0
    koi_count = 0
    armourbit_count = 0
    msg = 0
    robotbit_tags = []
    koi_tags = []
    armourbit_tags = []
    robotbit_tags.append("rfid")
    koi_tags.append("rfid")
    armourbit_tags.append("rfid")
    armourbit_count = 0
    koi_count = 0
    robotbit_count = 0
    robot = robotbit.RobotBit()
    screen.sync = 1
    wifi.connect(str("name"), "pwd")
    mqtt = mqttsimple.MQTTClient("mqtt.makercloud.io", "future",port=1883)
    mqtt.connect()
    screen.sync = 0
    screen.fill((0, 0, 0))
    screen.text(str("Place RFID Tag"),5,10,1,(0, 119, 255))
    screen.refresh()
    mqtt.publish("/topic", str("_dn=future,_dsn=future,robotbit=")+str(robotbit_count))
    sleep(1)
    mqtt.publish("/topic", str("_dn=future,_dsn=future,koi=")+str(koi_count))
    sleep(1)
    mqtt.publish("/topic", str("_dn=future,_dsn=future,armourbit=")+str(armourbit_count))
    sleep(1)
    while True:
      if sensor.btnValue('a'):
        robot.motor(1,170)
      if sensor.btnValue('b'):
        robot.motor(1,0)
      RFID().probe(probeCallback if 'probeCallback' in dir() else None)
      sleep(0.5)

[Sample Program](https://github.com/kittenbothk/kittenbothk/blob/master/Kits/inventory_system/images/code_makercloud_futureboard.py)

### Model Instructions

1. Fill in Wifi login information and MakerCloud MQTT topics
2. Fill in the corresponding RFID ID for the product
3. Download the program and turn on the power, wait for the futureboard to connect to the internet
4. Press A to turn on the conveyor belt, B to turn if off
5. When the RFID Sensor detects a RFID chip, Futureboard will display the ID and uploads the information to MakerCloud

## ObjectBlocks Sample Program

### KittenBlock

![](./images/code_objectblocks_futureboard.png)

[Sample Program](https://github.com/kittenbothk/kittenbothk/blob/master/Kits/inventory_system/images/code_objectblocks_futureboard.sb3)

### Python

    #/bin/python

    from time import sleep
    from future import *
    from sugar import *
    import mqttsimple
    import robotbit
    def probeCallback():
      global id,robotbit_count,koi_count,armourbit_count,msg
      id = RFID().uuid()
      if id in robotbit_tags:
        msg = "Robotbit."
        robotbit_count += 1
        mqtt.publish("/topic", robotbit_count)
      else:
        if id in koi_tags:
          msg = "KOI."
          koi_count += 1
          mqtt.publish("/topic", koi_count)
        else:
          if id in armourbit_tags:
            msg = "ArmourBit."
            armourbit_count += 1
            mqtt.publish("/topic", armourbit_count)
      sleep(1)
      screen.fill((0, 0, 0))
      screen.text(str("Place RFID Tag"),5,10,1,(0, 119, 255))
      screen.text(str(id),5,30,2,(0, 119, 255))
      screen.refresh()
      mqtt.publish("/topic", str(msg)+str(id))

    id = 0
    robotbit_count = 0
    koi_count = 0
    armourbit_count = 0
    msg = 0
    robotbit_tags = []
    koi_tags = []
    armourbit_tags = []
    robotbit_tags.append("rfid")
    koi_tags.append("rfid")
    armourbit_tags.append("rfid")
    armourbit_count = 0
    koi_count = 0
    robotbit_count = 0
    robot = robotbit.RobotBit()
    screen.sync = 1
    wifi.connect(str("name"), "pwd")
    mqtt = mqttsimple.MQTTClient("hub2.objectblocks.cc", "id",user=str("name"), password=str("password"),port=1883)
    mqtt.connect()
    screen.sync = 0
    screen.fill((0, 0, 0))
    screen.text(str("Place RFID Tag"),5,10,1,(0, 119, 255))
    screen.refresh()
    mqtt.publish("/topic", robotbit_count)
    sleep(1)
    mqtt.publish("/topic", koi_count)
    sleep(1)
    mqtt.publish("/topic", armourbit_count)
    sleep(1)
    while True:
      if sensor.btnValue('a'):
        robot.motor(1,170)
      if sensor.btnValue('b'):
        robot.motor(1,0)
      RFID().probe(probeCallback if 'probeCallback' in dir() else None)
      sleep(0.5)

[Sample Program](https://github.com/kittenbothk/kittenbothk/blob/master/Kits/inventory_system/images/code_objectblocks_futureboard.py)

### Model Instructions

1. Fill in Wifi login information and Objectblocks MQTT topics
2. Fill in the corresponding RFID ID for the product
3. Download the program and turn on the power, wait for the futureboard to connect to the internet
4. Press A to turn on the conveyor belt, B to turn if off
5. When the RFID Sensor detects a RFID chip, Futureboard will display the ID and uploads the information to Objectblocks

## ThingSpeak Sample Program

### KittenBlock

![](./images/code_objectblocks_futureboard.png)

[Sample Program](https://github.com/kittenbothk/kittenbothk/blob/master/Kits/inventory_system/images/code_thingspeak_futureboard.sb3)

### Python

    #/bin/python
    
    from time import sleep
    from future import *
    from sugar import *
    import mqttsimple
    import robotbit
    def probeCallback():
      global id,robotbit_count,koi_count,armourbit_count,msg
      id = RFID().uuid()
      if id in robotbit_tags:
        robotbit_count += 1
        mqtt.publish("channels//publish", str("field1=")+str(robotbit_count))
      else:
        if id in koi_tags:
          koi_count += 1
          mqtt.publish("channels//publish", str("field2=")+str(koi_count))
        else:
          if id in armourbit_tags:
            armourbit_count += 1
            mqtt.publish("channels//publish", str("field3=")+str(armourbit_count))
      sleep(1)
      screen.fill((0, 0, 0))
      screen.text(str("Place RFID Tag"),5,10,1,(0, 119, 255))
      screen.text(str(id),5,30,2,(0, 119, 255))
      screen.refresh()

    id = 0
    robotbit_count = 0
    koi_count = 0
    armourbit_count = 0
    msg = 0
    robotbit_tags = []
    koi_tags = []
    armourbit_tags = []
    robotbit_tags.append("rfid")
    koi_tags.append("rfid")
    armourbit_tags.append("rfid")
    armourbit_count = 0
    koi_count = 0
    robotbit_count = 0
    robot = robotbit.RobotBit()
    screen.sync = 1
    wifi.connect(str("name"), "pwd")
    mqtt = mqttsimple.MQTTClient("mqtt3.thingspeak.com", "id",user=str("name"), password=str("password"),port=1883)
    mqtt.connect()
    screen.sync = 0
    screen.fill((0, 0, 0))
    screen.text(str("Place RFID Tag"),5,10,1,(0, 119, 255))
    screen.refresh()
    mqtt.publish("channels//publish", str("field1=")+str(robotbit_count))
    sleep(1)
    mqtt.publish("channels//publish", str("field2=")+str(koi_count))
    sleep(1)
    mqtt.publish("channels//publish", str("field3=")+str(armourbit_count))
    sleep(1)

    while True:
      if sensor.btnValue('a'):
        robot.motor(1,170)
      if sensor.btnValue('b'):
        robot.motor(1,0)
      RFID().probe(probeCallback if 'probeCallback' in dir() else None)
      sleep(0.5)

[Sample Program](https://github.com/kittenbothk/kittenbothk/blob/master/Kits/inventory_system/images/code_thingspeak_futureboard.py)


### Model Instructions

1. Fill in Wifi login information and ThingSpeak MQTT topics
2. Fill in the corresponding RFID ID for the product
3. Download the program and turn on the power, wait for the futureboard to connect to the internet
4. Press A to turn on the conveyor belt, B to turn if off
5. When the RFID Sensor detects a RFID chip, Futureboard will display the ID and uploads the information to ThingSpeak
    

    Note: ThingSpeak only supports numeric data so item ID and item name is not supported in this program