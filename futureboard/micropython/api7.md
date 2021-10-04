# Programming with MicroPython: WiFi & IoT

## Import FutureBoard Library

Import the Library to make use of its functions.

    from future import *
    
## 07:  WiFi & IoT

### 1. Connect to WiFi

    wifi.connect('router','password')
    
FutureBoard can only connect to wireless networks with 2.4GHz frequency.

### 2. Get the Connection Status

    wifi.sta.isconnected()
    
Returns 1 if FutureBoard is connected to the network, 0 if not.

### 3. Get the Connection Configuration

    wifi.sta.ifconfig()
    
Returns a list with the configuration including IP Address, Subnet Mask, Gateway, Domain.
    
### 4. Get the MAC Address
    
    import machine
    import ubinascii

    x = ubinascii.hexlify(machine.unique_id()).decode().upper()
    
Returns the physical address of the FutureBoard.

### Sample Program 1~4

    #/bin/python
    from future import *

    from time import sleep
    
    import machine
    import ubinascii

    wifi.connect(str("name"), "pwd")
    sleep(5)
    if wifi.sta.isconnected():
      screen.clear()
      screen.text(str("IP: ")+str(wifi.sta.ifconfig()[0]),5,10,1,(0, 119, 255))
      screen.text("MAC Address: ",5,25,1,(0, 119, 255))
      screen.text(ubinascii.hexlify(machine.unique_id()).decode().upper(),5,35,1,(0, 119, 255))
      screen.text("Subnet Mask: ",5,50,1,(0, 119, 255))
      screen.text(wifi.sta.ifconfig()[1],5,60,1,(0, 119, 255))
      screen.text(str("Gateway: ")+str(wifi.sta.ifconfig()[2]),5,75,1,(0, 119, 255))
      screen.text(str("DNS: ")+str(wifi.sta.ifconfig()[3]),5,90,1,(0, 119, 255))

## Import MQTT Library

    import mqttsimple
    
MQTT operations require the mqttsimple library.
    
### 5. Set up an MQTT object

    myMQTT = mqttsimple.MQTTClient(server,client_id,port=0,user=None,password=None,keepalive=0,ssl=False,ssl_params={})

Creates an object with the connection to the MQTT Broker.

For most brokers, insert the host address into server and the client id into client_id.

For some brokers, please refer to the broker's documentations for the details required to connect to the server.
    
### 6. Connect to the MQTT Server

    myMQTT.connect()

### 7. Disconnect the MQTT Server

    myMQTT.disconnect()
    
### 8. Subscribe to a MQTT Topic
    
    myMQTT.subscribe(topic=)
    
Fill in the topic name according to the documentation of the MQTT Broker.

### 9. Publish a Message to a MQTT Topic

    myMQTT.publish(topic,msg)
    
Fill in the message and topic name according to the documentation of the MQTT Broker.

### 10. Read the Message from the MQTT Topic

    myMQTT.mqttRead(topic)

Fill in the topic name according to the documentation of the MQTT Broker.

### 11. Read the Last Message of the MQTT Topic

    myMQTT.check_msg()
    
### 12. Wait until a MQTT Message is Published

    myMQTT.wait_msg()
    
### 13. Define MQTT Event Trigger Function


    def myFunction(topic,msg):
        print(topic)
        print(msg)

    myMQTT.set_callback(myFunction())

### Sample Program 1
    
    import mqttsimple
    if not(wifi.sta.isconnected()):
        wifi.connect('router', 'password') 
    
    c = mqttsimple.MQTTClient("myServer", 'myID')
    c.connect() 

    c.subscribe('/topic1')
    
    x= 0
    # mqttRead() returns None if no new message is found
    while 1:
        if sensor.btnValue('a'):
            x+=1
            c.publish('/topic1','x'+str(x))
            sleep(0.2)
        # Print message if message is not None
        mqttT = c.mqttRead('/topic1')
        if mqttT:
            print(mqttT)

### Sample Program 2

    import mqttsimple
    if not(wifi.sta.isconnected()):
        wifi.connect('router', 'password') 
    
    c = mqttsimple.MQTTClient("myServer", 'myID')
    c.connect() 
    
    # Automacically triggered when topic is updated
    def sub_cb(topic, msg):
        print((topic, msg))   
    c.set_callback(sub_cb)
        
    c.subscribe('/ttt')
    
    while 1:
        if sensor.btnValue('a'):
            c.publish('/ttt', 'hello')
            sleep(0.2)
        # check message
        c.check_msg()
    
    # try below for waiting until message update
    # c.wait_msg()
