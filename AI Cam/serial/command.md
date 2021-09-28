# KOI Serial Command API

KOI can be used alongside any MCU capable of serial communication by sending a serial command, this section contains all the command available for the KOI.

The examples provided are in micropython for the Micro:bit, please adapt for the MCU of your preference.

## Get Firmware Version

Command: K0

Function: Gets the firmware version of KOI

Returns: K0 (Firmware Version)

    from microbit import *
    
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    uart.write('K0\r\n')
    sleep(100)
    ret_list = []
    
    if uart.any():
        ret = str(uart.readline(), 'UTF-8')
        ret = ret.strip()
        ret_list = ret.split(' ')
        
    if len(ret_list)>1:
        display.scroll(ret_list[1])

## Taking and Showing Photos

Command: K1 (name.jpg)

Function: Saves the picture with file name.

Command: K2 (name.jpg)

Function: Shows the picture with filename

    from microbit import *

    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)

    while True:
        if button_a.is_pressed():
            uart.write('K2 pic.jpg\r\n')
        if button_b.is_pressed():
            uart.write('K1 pic.jpg\r\n')
            
## KOI Button Status

Command: K3

Function: Returns the button status of the 2 buttons

Returns: K3  (Button A Status)  (Button B Status)

    from microbit import *

    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    ret_list = []

    while True:
        uart.write('K3\r\n')
        sleep(1000)
        if uart.any():
            ret = str(uart.readline(), 'UTF-8')
            ret = ret.strip()
            ret_list = ret.split(' ')
        if len(ret_list)>1:
            display.scroll('A:')
            display.scroll(ret_list[1])
            display.scroll('B:')
            display.scroll(ret_list[2])
            
## Display String

Command: K4 x y delay string

Function: Displays sting at (x,y) with a duration determined by delay

    from microbit import *

    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    uart.write('K4 0 0 1000 KOI\r\n')
    
## Change LCD Orientation

Command: K6 direction

Function: Changes LCD orientation

Direction: 
- 0: Front Camera
- 1: Back Camera


    from microbit import *

    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)

    while True:
        if button_a.is_pressed() and button_b.is_pressed():
            uart.write('K6 2\r\n')
        if button_a.is_pressed():
            uart.write('K6 0\r\n')
        if button_b.is_pressed():
            uart.write('K6 1\r\n')
            
## Circle Tracking

Command: K10 threshold

Function: Tracks the circle on screen, adjust threshold to the sensitivity, the default is 4000.

Returns: K10  (Center X)  (Center Y)  (Radius)

    from microbit import *

    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)

    while True:
        if button_a.is_pressed():
            uart.write('K10 3000\r\n')
            sleep(1000)
        if uart.any():
            ret = str(uart.readline(), 'UTF-8')
            ret = ret.strip()
            ret_list = ret.split(' ')
            if len(ret_list)>1:
                display.scroll('X:')
                display.scroll(ret_list[1])
                display.scroll('Y:')
                display.scroll(ret_list[2])
                display.scroll('R:')
                display.scroll(ret_list[3])
                
## Rectangle Tracking

Command: K11 threshold

Function: Tracks the rectangle on screen, adjust threshold to the sensitivity, the default is 4000.

Returns: K11  (Center X)  (Center Y)  (width)  (Height)

    from microbit import *

    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)

    while True:
        if button_a.is_pressed():
            uart.write('K11 6000\r\n')
            sleep(1000)
        if uart.any():
            ret = str(uart.readline(), 'UTF-8')
            ret = ret.strip()
            ret_list = ret.split(' ')
            if len(ret_list)>1:
                display.scroll('X:')
                display.scroll(ret_list[1])
                display.scroll('Y:')
                display.scroll(ret_list[2])
                display.scroll('W:')
                display.scroll(ret_list[3])
                display.scroll('H:')
                display.scroll(ret_list[4])
                
## Linear Regression

Command: K16 color

Function: Calibrates to the color of the line, color refers to color name, the color name is just for reference.

Command: K12 color

Function: Tracks the line using linear regression and the given color name.

Returns: K12  (X1)  (Y1)  (X2)  (Y2)

    from microbit import *

    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    flag=False

    while True:
        if button_a.is_pressed():
            uart.write('K16 test\r\n')
            sleep(2000)
            flag=True
        if flag:
            uart.write('K12 test\r\n')
            sleep(500)
            if uart.any():
                ret = str(uart.readline(), 'UTF-8')
                ret = ret.strip()
                ret_list = ret.split(' ')
                if len(ret_list)>1:
                    display.scroll('X1:')
                    display.scroll(ret_list[1])
                    display.scroll('Y1:')
                    display.scroll(ret_list[2])
                    display.scroll('X2:')
                    display.scroll(ret_list[3])
                    display.scroll('Y2:')
                    display.scroll(ret_list[4])
                sleep(2000)

## Color Blob Tracking

Command: K16 color

Function: Calibrates to the color of the blob, color refers to color name, the color name is just for reference.

Command: K15 color

Function: Tracks the color blob with the given color name.

Returns: K5  (X)  (Y)  (W)  (H)

    from microbit import *

    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    flag=False

    while True:
        if button_a.is_pressed():
            uart.write('K16 test\r\n')
            sleep(2000)
            flag=True
        if flag:
            uart.write('K15 test\r\n')
            sleep(500)
            if uart.any():
                ret = str(uart.readline(), 'UTF-8')
                ret = ret.strip()
                ret_list = ret.split(' ')
                if len(ret_list)>1:
                    display.scroll('X:')
                    display.scroll(ret_list[1])
                    display.scroll('Y:')
                    display.scroll(ret_list[2])
                    display.scroll('W:')
                    display.scroll(ret_list[3])
                    display.scroll('H:')
                    display.scroll(ret_list[4])
                sleep(2000)
                
## Read QR Code and Barcode

Command: K20

Function: Reads a QR Code

Returns: K20  (Content)

Command: K22

Function: Reads a Barcode

Returns: K22 (Content)

    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed():
            uart.write('K20\r\n')
            sleep(500)
        if button_b.is_pressed():
            uart.write('K22\r\n')
            sleep(500)
        if uart.any():
            ret = str(uart.readline(), 'UTF-8')
            ret = ret.strip()
            ret_list = ret.split(' ')
            if len(ret_list)>1:
                display.scroll(ret_list[1])
                ret_list=[]

## Face Detection

Command: K30

Function: Loads the face model for face detection.

Command: K31

Function: Face Detection for once

Returns: K0  (ID)  (X)  (Y)

Command: K32

Function: Gets the number of detected faces

Returns: K32  (faces)

    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    uart.write('K30\r\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed():
            uart.write('K31\r\n')
            sleep(500)
        if uart.any():
            ret = str(uart.readline(), 'UTF-8')
            ret = ret.strip()
            ret_list = ret.split(' ')
            if len(ret_list)>1:
                display.scroll('X')
                display.scroll(ret_list[2])
                display.scroll('Y')
                display.scroll(ret_list[3])
                ret_list=[]
                     
## Image Classifier

Command: K40

Function: Initiates the Image Classifier

Command: K41 className

Function: Adds a class with className as tag

Command: K42

Function: Image Classify

Returns: K42  (className)
    
    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    uart.write('K40\r\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed() and button_b.is_pressed():
            uart.write('K42\r\n')
            sleep(500)
        if button_a.is_pressed():
            uart.write('K41 rock\r\n')
            sleep(500)
        if button_b.is_pressed():
            uart.write('K41 paper\r\n')
            sleep(500)
        if uart.any():
            ret = str(uart.readline(), 'UTF-8')
            ret = ret.strip()
            ret_list = ret.split(' ')
            if len(ret_list)>1:
                display.scroll(ret_list[1])
                ret_list=[]

Command: K43 name.json

Function: Saves the model to the SD Card, file extension can be json or bin.

    from microbit import *
    
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    uart.write('K40\r\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed() and button_b.is_pressed():
            uart.write('K43 test.json\r\n')
            sleep(500)
        if button_a.is_pressed():
            uart.write('K41 rock\r\n')
            sleep(500)
        if button_b.is_pressed():
            uart.write('K41 paper\r\n')
            sleep(500)        
            
Command: K44 name.json

Function: Loads the model from the SD card.

    from microbit import *
    
    ret_list=[]
    
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    uart.write('K40\r\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed() and button_b.is_pressed():
            uart.write('K44 test.json\r\n')
            sleep(500)
        if button_a.is_pressed():
            uart.write('K42\r\n')
            sleep(500)
            if uart.any():
                ret = str(uart.readline(), 'UTF-8')
                ret = ret.strip()
                ret_list = ret.split(' ')
                if len(ret_list)>1:
                    display.scroll(ret_list[1])
                    ret_list=[]
                
## WiFi and IoT

Command: K50 SSID password

Function: Connects to a WiFi network with the given SSID and password.(Only 2.4GHz network is supported)

Command: K54

Command: Displays the IP Address on the screen

    from microbit import *
    
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    uart.write('K50 SSID password\r\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed():
            uart.write('K54\r\n')
            sleep(500)

Command: K51 mqttHost clientID port [username] [password]

Function: Connects to a MQTT Broker.
    
    Username and password are only needed if the broker requires authentication.

Command: K52 topic

Function: Subscribes a MQTT topic

Command: K53 topic message

Function: Publishes a message to a MQTT topic

Command: K55 topic

Function: Reads data from a MQTT topic

Returns: K55  (message)
        
    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    uart.write('K50 SSID password\r\n')
    sleep(500)
    uart.write('K51 mqttHost clientID port [username] [password]\r\n')
    sleep(500)
    uart.write('K52 topic\r\n')
    sleep(500)
    
    while True:
        if button_a.is_pressed():
            uart.write('K53 topic message\r\n')
            sleep(500)
        if button_b.is_pressed():
            uart.write('K55 topic\r\n')
            sleep(500)
                if uart.any():
                    ret = str(uart.readline(), 'UTF-8')
                    ret = ret.strip()
                    ret_list = ret.split(' ')
                    if len(ret_list)>1:
                        display.scroll(ret_list[1])
                        ret_list=[]

## Recording and Playback

Command: K61 sound.wav

Function: Records a sound clip and saves to SD card

Command: K62 sound.wav

Function: Playbacks a sound clip from SD card.
    
    from microbit import *
    
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    
    while True:
        if button_a.is_pressed():
            uart.write('K61 hello.wav\r\n')
            sleep(500)
        if button_b.is_pressed():
            uart.write('K62 hello.wav\r\n')
            sleep(500)

## Voice Recognition

Command: K63 

Function: Calibrates the noise level

Command: K64 id

Function: Adds a command with id as tag.
    
Command: K65

Function: Recognizes a command.

Returns: K65  (id)

    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    uart.write('K63\r\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed() and button_b.is_pressed():
            uart.write('K65\r\n')
            sleep(500)
        if button_a.is_pressed():
            uart.write('K64 hi\r\n')
            sleep(500)
        if button_b.is_pressed():
            uart.write('K64 bye\r\n')
            sleep(500)
        if uart.any():
            ret = str(uart.readline(), 'UTF-8')
            ret = ret.strip()
            ret_list = ret.split(' ')
            if len(ret_list)>1:
                display.scroll(ret_list[1])
                ret_list=[]
                
Command: K66 sound.json

Function: Saves the model to the SD Card.

    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    uart.write('K63\r\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed() and button_b.is_pressed():
            uart.write('K66 greeting.json\r\n')
            sleep(500)
        if button_a.is_pressed():
            uart.write('K64 hi\r\n')
            sleep(500)
        if button_b.is_pressed():
            uart.write('K64 bye\r\n')
            sleep(500)
    
Command: K67 sound.json

Function: Loads a model from SD Card.

    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    uart.write('K63\r\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed():
            uart.write('K65\r\n')
            sleep(500)
        if button_b.is_pressed():
            uart.write('K67 greeting.json\r\n')
            sleep(500)
        if uart.any():
            ret = str(uart.readline(), 'UTF-8')
            ret = ret.strip()
            ret_list = ret.split(' ')
            if len(ret_list)>1:
                display.scroll(ret_list[1])
                ret_list=[]


## Face Recognition

Command: K75 

Function: Runs face recognition. (Internet Connection Required)

Returns: K75  (token)  (age)  (gender)  (masked)  (emotion)

Command: K76 token groupName faceName

Function: Adds the face token into a group with a given name.
    
Command: K77 token groupName

Function: Searches a person in a group with a face token.

Returns: K77  faceName

    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    uart.write('K50 SSID password\r\n')
    sleep(1000)
    
    def faceHandle(flag):
        if uart.any():
            ret = str(uart.readline(), 'UTF-8')
            ret = ret.strip()
            ret_list = ret.split(' ')
            if len(ret_list)>1:
                if flag=='add':
                    token=ret_list[1]
                    uart.write('K76 %s myFriends Mary\r\n' % token)
                    sleep(500)
                    ret_list=[]
                if flag=='search':
                    token=ret_list[1]
                    uart.write('K77 %s myFriends\r\n' % token)
                    sleep(500)
                    faceHandle('return')
                if flag=='return':
                    display.scroll(ret_list[1])
                    ret_list=[]
    
    while True:
        if button_a.is_pressed():
            uart.write('K75\r\n')
            sleep(500)
            faceHandle('add')
            
        if button_b.is_pressed():
            uart.write('K75\r\n')
            sleep(500)
            faceHandle('search')
                
## Text to Speech

Command: K78 string

Function: Text to speech. (Internet Connection Required)

    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    uart.write('K50 SSID password\r\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed():
            uart.write('K78 hello\r\n')
            sleep(500)
            
        if button_b.is_pressed():
            uart.write('K78 9999\r\n')
            sleep(500)
            
## KPU Stop

Command: K98

Function: Stops the KPU(Image Classifier/Face Detection)

    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed():
            uart.write('K98\r\n')
            sleep(500)

## KOI Restart

Command: K99

Function: Restarts the KOI

    from microbit import *
    
    ret_list=[]
    uart.init(baudrate=115200, tx=pin1, rx=pin2)
    uart.write('\n\n')
    sleep(1000)
    
    while True:
        if button_a.is_pressed():
            uart.write('K99\r\n')
            sleep(500)