# Inventory System Sample Program(FutureBoard)

## RFID Chip Program

Use this program to check the ID of the RFID chips.

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
      sleep(0.2)

[Sample Program](https://raw.githubusercontent.com/kittenbothk/kittenbothk/master/Kits/inventory_system/py/uuid.py)

## RFID Read/Write Program

Use this program to write or read data to the RFID tags. Press A to write data, press B to read data.

    from future import *
    import sugar
    from time import sleep
    
    rfid = sugar.RFID()
    
    while 1:
        if sensor.btnValue('a'):
            rfid.write(1, 1, 'ITEM')
            sleep(1)
        elif sensor.btnValue('b'):
            print(rfid.read(1, 1))
            sleep(1)

[Sample Program](https://raw.githubusercontent.com/kittenbothk/kittenbothk/master/Kits/inventory_system/py/RFID_read_write.py)

## MakerCloud Sample Program

    from future import *
    from robotbit import RobotBit
    from sugar import *
    from time import sleep
    from mqttsimple import MQTTClient
    
    id=''
    item=''
    msg=''
    mc_prefix='_dn=,_dsn=,'
    
    koi_count=0
    asr_count=0
    
    def probeCallback():
        global koi_count
        global asr_count
        rb.motor(1,1)
        screen.clear()
        id=RFID().uuid()
        print(id)
        screen.text(id,5,40,2,(255,255,255))
        item=RFID().read(1, 1)
        print(item)
        screen.text(item,5,10,2,(255,255,255))
        msg=item+'.'+id
        print(mc_prefix+msg)
        makercloud.publish("",str(mc_prefix+'item='+msg))
        sleep(1)
        if (item=='koi'):
            koi_count+=1
            makercloud.publish("",mc_prefix+'koi_count='+str(koi_count))
        elif (item=='asr'):
            asr_count+=1
            makercloud.publish("",mc_prefix+'asr_count='+str(asr_count))
        rb.motor(1,-50)
        sleep(2)
    
    rb=RobotBit()
    
    wifi.connect('','')
    sleep(3)
    makercloud=MQTTClient("mqtt.makercloud.io", "clientID")
    makercloud.connect()
    
    makercloud.publish("",mc_prefix+'asr_count='+str(asr_count))
    sleep(1)
    makercloud.publish("",mc_prefix+'koi_count='+str(koi_count))
    
    screen.clear()
    
    while True:
        if sensor.btnValue('a'):
            rb.motor(1,-50)
        if sensor.btnValue('b'):
            rb.motor(1,0)
        RFID().probe(probeCallback if 'probeCallback' in dir() else None)
        sleep(0.2)

[Sample Program](https://raw.githubusercontent.com/kittenbothk/kittenbothk/master/Kits/inventory_system/py/conveyor_belt.py)

### Model Instructions

1. Fill in Wifi login information and MakerCloud MQTT topics
2. Fill in the corresponding RFID number for the product
3. Download the program and turn on the power, wait for the LED to completely light up
4. Press A to turn on the conveyor belt, B to turn if off
5. When the RFID Sensor detects a RFID chip, Micro:bit will display the ID and uploads the information to MakerCloud.

