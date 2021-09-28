# KOI MicroPython API

Please refer to this page on how to utilize the various functions of the KOI using micropython.

## Importing KOI library

    from koi import *

## Basics

### LCD Orientation

    lcd.rotation(0)
    
Changes LCD orientation.

- 0 for front facing, 1 for back facing.

### Drawing Strings

    drawString(x, y, string, delay)
    
Draws a string on the LCD.

- X, Y: Coordinates represent top left corner of string.
- String: String.
- Delay: Text duration.

### Taking and showing pictures

    img.save("s1.jpg")
    loadImage("s1.jpg")
    
Taking and showing pictures.

### Getting button values

    btnAValue()
    btnBValue()
    
Obtains button values.

- Returns 1 when pressed, 0 when not pressed.

### Sample Program

    #/bin/python
    from koi import *
    
    from time import sleep
    
    x = 0
    
    lcd.rotation(2)     #Change LCD orientation
    sleep(1)
    lcd.rotation(0)     #Change LCD orientation
    sleep(1)
    drawString(5,5,"hello world",500)       #Show String
    while True:
      img=sensor.snapshot()     #Enables screen refresh
      lcd.display(img)          #Enables screen refresh
      if btnAValue() == 1:
        img.save("s1.jpg")      #Takes picture
      if btnBValue() == 1:
        loadImage("s1.jpg")     #Shows picture
        
## Image Classifier

### Initiate Classifier

    cla.reset()
    
Initiates the classifier.

### Feature extraction

    cla.addImage("tag")

Extract features and add tag.

- tag: object name, maximum 40 items, 40 pictures

### Image Classifying

    cla.getImageTag()
    
Classify the image, returns tag.

### Classifier Event Triggers

    while cla.getImageTag()=='tag':
        pass
    
Triggers an event on classification.

### Saving and Loading Classifier Models

    cla.save("abc.json")
    cla.load("abc.json")
    
Save or load classifier models.

### Sample Program

    #Model Training
    from koi import *
    
    x=0
    
    cla.reset()     #Init classifier
    
    while True:
        img=sensor.snapshot()   #Enables screen refresh
        lcd.display(img)        #Enables screen refresh
        if btnAValue():
            cla.addImage('apple')       #Add tag
        if btnBValue():
            cla.addImage('orange')      #Add tag
        if btnAValue() and btnBValue():
            cla.save('fruit.json')      #Save Model
        time.sleep(0.1)

---
    #Model Running
    from koi import *
    
    x=0
    cla.reset()         #init classifier
    cla.load("fruit.json")      #Load Model
    
    while True:
        img=sensor.snapshot()   #Enables screen refresh
        lcd.display(img)        #Enables screen refresh
        if btnAValue():
            tag=cla.getImageTag()       #Classify
            if tag=='orange':
                print('I like oranges.')
            elif tag=='apple':
                print('Apples are healthy.')
        time.sleep(0.1)
    
## Face Detection

### Load Face Model

    yoloinit()

Load face model.

### Track face

    trackface()

Tracks the face, returns a list.

### 示範程式

    #/bin/python
    from koi import *
    
    x = 0
    face_prop=[0,0]
    
    yoloinit()          #Load Face model
    while True:
        img=sensor.snapshot()   #Enables screen refresh
        lcd.display(img)        #Enables screen refresh
        r = trackface()         #Tracks the face
        if r:
            is_face=1
            drawString(5,5,r,500)
            face_prop[0]=(r[0][2]+r[0][0])/2
            face_prop[1]=(r[0][3]+r[0][1])/2
        else:
            is_face=0
            
        while is_face:
            print('X: '+str(face_prop[0]))
            print('Y: '+str(face_prop[1]))
            is_face=0
        time.sleep(0.5)
    
## Geometric Shape Tracking

### Track Lines

    findLines()
    
Find lines, returns a list.

### Track Circles
    
    findCircle(threshold)
    
Find circles, returns a list.

- threshold: adjust this value to adjust sensitivity, default is 4000.

### Track Rectangles

    findRect(threshold)
    
Find rectangles, returns a list.

- threshold: adjust this value to adjust sensitivity, default is 4000.

### Sample Program

    from koi import *

    x=0
    
    while True:
        img=sensor.snapshot()   #Enables screen refresh
        lcd.display(img)        #Enables screen refresh
        if btnAValue() and btnBValue():
            line_prop = findLines()     #Find lines
            print(line_prop[0])
            time.sleep(0.1)
        elif btnAValue():
            circle_prop = findCircle(4000)    #Find Circles
            print(circle_prop[0])
            time.sleep(0.1)
        elif btnBValue():
            rect_prop = findRects(4000)       #Find Rectangles
            print(rect_prop[0])
            time.sleep(0.1)
            
## Color Blob Tracking

### Calibrates Color

    colorCalibrate()
    
Calibrates color for tracking.

### Finds Color Blob

    findBlob()
    
Finds color blob, returns a list.

### Finds Line

    findLinearRegress()
    
Finds line, returns a list.

### Sample Program

    from koi import *
    
    x=0
    
    while True:
        img=sensor.snapshot()   #Enables screen refresh
        lcd.display(img)        #Enables screen refresh
        if btnAValue():
            colorCalibrate()        #Color Calibration
            time.sleep(0.1)
        elif btnBValue():
            blob_prop=findBlob()        # Finds Color Blob  
            print(blob_prop[0])
            time.sleep(0.1)
        elif btnAValue() and btnBValue():
            line_prop=findLinearRegress()       #Finds Line
            print(line_prop[0])
            time.sleep(0.1)
            
## Barcode and QR code Recognition

### QR Code Recognition

    findQRCode()

Finds QR code, returns content of QR code.

### Barcode Recognition

    findBarcode()

Finds Barcode, returns content of barcode.

### AprilTag Recognition

    findAprilTag()

Finds Apriltag, returns content of Apriltag.

### Sample Program

    from koi import *

    x=0
    
    lcd.rotation(2)
    
    while True:
        img=sensor.snapshot()   #Enables screen refresh
        lcd.display(img)        #Enables screen refresh
        if btnAValue():
            barcode=findBarCode()       #Barcode
            print(barcode[0][4])
            time.sleep(0.1)
        if btnBValue():
            qrcode=findQRCode()     #QR Code
            print(qrcode[0][4])
            time.sleep(0.1)
        if btnAValue() and btnBValue():
            april=findAprilTag()        #AprilTag
            print(april[0])
            time.sleep(0.1)
            
## Voice Recognition

### Record and Play

    speech.recordWav('hi.wav')
    speech.playWav('hi.wav')
    
Records and plays a wav file.

### Calibrates Noise Level

    speech.noiseTap()

Calibrates the noise level, mandatory before voice recognition.

### Adds Voice Command

    speech.addCommand('hi')
    
Adds a voice command.

### Recognizes Voice Command

    speech.getCommand()
    
Recognizes and returns the command.

### Saves Voice Model

    speech.saveClass('name.json')

Saves the voice model.

### Loads Voice Model

    speech.loadClass('name.json')

Loads the voice model.

### Sample Program

    # Rec and Play
    from koi import *

    x=0

    while True:
        img=sensor.snapshot()   #Enables screen refresh
        lcd.display(img)        #Enables screen refresh
        if btnAValue():
            speech.recordWav('hi.wav')      #Record
            time.sleep(0.1)
        if btnBValue():
            speech.playWav('hi.wav')        #Play
            time.sleep(0.1)
            
---    
    
    #Voice Recognition
    from koi import *
    
    x=0
    
    speech.noiseTap()       #Calibrate
    
    while True:
        img=sensor.snapshot()   #Enables screen refresh
        lcd.display(img)        #Enables screen refresh
        if btnAValue():
            speech.addCommand("hello")      #Add command
            time.sleep(0.1)
        if btnBValue():
            speech.addCommand("bye")    #Add command
            time.sleep(0.1)
        if btnAValue() and btnBValue():
            print(speech.getCommand())      #Recognize
            time.sleep(0.1)
            
## IoT

### Connecting to WiFi

    wifi.joinap(str("apname"),str("password"))
    
Connects to WiFi.
    
### IP Address

    wifi.ipaddr()
    
Return IP address.

### Connects to MQTT Broker.

    wifi.mqtthost(host)
    
Connects to MQTT Broker.

- host: MQTT host address

### Subscribes Topic

    wifi.mqttsub(topic)

Subscribes a topic on MQTT.
  
- topic: topic to subscribe

### Publishes Message to Topic

    wifi.mqttsub(topic, message)
    
Publishes a message to topic.

- topic: topic to publish.
- message: message to publish.

### Reads MQTT message

    wifi.mqttread(topic)

Reads topic message.

- topic: topic to read from, returns a list.

### Sample Program

    from koi import *
    
    wifi.joinap(str("apname"),str("password"))      #WiFi
    time.sleep(2)
    print(wifi.ipaddr())    #IP
    time.sleep(2)
    wifi.mqtthost("127.0.0.1")      #MQTT
    wifi.mqttsub("test01")      #Subscribe
    
    while True:
        img=sensor.snapshot()    #Enables screen refresh
        lcd.display(img)         #Enables screen refresh
        if btnAValue():
            wifi.mqttpub("test01","hello world")    #Publish
        if btnBValue():
            msg=wifi.mqttread("test01")     #Read
            print("Message: "+msg[0])
            print("Topic: "+msg[1])

## Face Recognition

### Face Recognition

    face=baiduFace(op=1)

Runs face recognition once.(WiFi required)
    
### Face Parameters

    face['parameter']

Returns result from face recognition.

parameter:

- face_token: unique face token for each face
- location: coordinates, size of face
- gender: gender of person
- expression: emotion of person
- angle: tilt angle of face
- mask: true if person is wearing a mask
- age: age of person
    
### Adding Faces to a Group

    baiduFace(op=2, token=face['face_token'], group="group", name="name")
    
Adds a face to the face group.
    
### Searching Faces from a Group

    baiduFace(op=3, token=face['face_token'], group="group")
    
Searches a face from a group, returns name and confidence.

### Sample Program

    from koi import *
    
    wifi.joinap(str("apname"),str("password"))
    time.sleep(2)
    
    while True:
        img=sensor.snapshot()   #Enables screen refresh
        lcd.display(img)        #Enables screen refresh
        if btnAValue():
            face=baiduFace(op=1)
            time.sleep(5)
            baiduFace(op=2, token=face['face_token'], group="group", name="name")   #add face
        if btnBValue():
            face=baiduFace(op=1)
            time.sleep(5)
            result=baiduFace(op=3, token=face['face_token'], group="name")  #search face
            print("Name: "+faceResult['result']['user_list'][0]['user_id'])
            print("Confidence: "+str(faceResult['result']['user_list'][0]['score']))
            
## Q&A

### KOI's display is laggy.

#### Please enable the screen refresh.

### KOI does not run the program I uploaded.

#### Please restart the KOI because it was still running the original main.py.

### Can I connect other modules using the 4-Pin Port?

#### No, this port is for connecting to Micro:bit only.

### KOI's LCD is reversed.

#### Please use the LCD orientation command.

