# Programming with MicroPython: Sugar and Powerbrick Modules

## Import Sugar Library

Import the Sugar library to make use of its functions.

    from sugar import *

## 14: Sugar and Powerbrick modules

## PIR Sensor

    # pin=['P0','P1','P2','P3','P8','P9','P12','P13','P14','P15','P16']

    value=PIR(pin).value()

Returns a boolean value from the PIR sensor.

- pin: The pin connected to the sensor.

## IR Line Tracker

    # pin=['P0','P1','P2','P3','P8','P9','P12','P13','P14','P15','P16']

    value=Tracker(pin).value()

Returns a boolean value from the Line Tracker.

- pin: The pin connected to the sensor.

## (Hall Effect)Magnet Sensor

    # pin=['P0','P1','P2','P3','P8','P9','P12','P13','P14','P15','P16']

    value=Hall(pin).value()

Returns a boolean value from the Magnet sensor.

- pin: The pin connected to the sensor.

## Button Sensor

    # pin=['P0','P1','P2','P3','P8','P9','P12','P13','P14','P15','P16']

    value=Button(pin).value()

Returns a boolean value from the Button sensor.

- pin: The pin connected to the sensor.

## LED Module

    # pin=['P0','P1','P2','P3','P8','P13','P14','P15','P16']
    # state=['ON','OFF']

    LED(pin).state(state) #ON/OFF

Sets the state of the LED module to be on or off.

    LED(pin).brightness(brightness) #Brightness

Sets the LED brightness.
 
- pin: The pin connected to the sensor.
- state: on/off.
- brightness: 0~100.

## Flame Sensor

    # pin=['P0','P1','P2','P3','P12','P14','P15','P16']

    value=Flame(pin).value()

Returns an analog value from the Flame sensor.

- pin: The pin connected to the sensor.

## Potentiometer Sensor

    # pin=['P0','P1','P2','P3','P12','P14','P15','P16']

    value=Angle(pin).value()

Returns an analog value from the Potentiometer sensor.

- pin: The pin connected to the sensor.

## Light Sensor

    # pin=['P0','P1','P2','P3','P12','P14','P15','P16']

    value=Light(pin).value()

Returns an analog value from the Light sensor.

- pin: The pin connected to the sensor.

## Soil Moisture Sensor

    # pin=['P0','P1','P2','P3','P12','P14','P15','P16']

    value=Soil(pin).value()

Returns an analog value from the Soil Moisture sensor.

- pin: The pin connected to the sensor.

## Water Sensor

    # pin=['P0','P1','P2','P3','P12','P14','P15','P16']

    value=WaterLevel(pin).value()

Returns an analog value from the Water sensor.

- pin: The pin connected to the sensor.

## Environment Sensor(Sugar)

    x=ENV().update()

    temperature=x[0]
    humidity=x[1]

Returns a list containing the temperature and humidity readings from the Environment sensor.

## TOF Laser Distance Module

    value=TOFDistance().value()

Returns the distance in mm from the laser distance module.

## Joystick Module
    
    # available positions
    # 'up', 'down', 'left', 'right', 'pressed'
    
    position=Joystick().state() #Joystick Position
    x_value=Joystick().value('x') #Joystick X value
    y_value=Joystick().value('y') #Joystick Y value

Returns the value from the Joystick module.

## RTC Clock Module

    Clock().setTime((year,month,day,weekday,hour,min,sec))

Sets the time on the Clock module.

    # available states
    # 'pause','open'

    Clock().modeSet(state=mode)

Starts or stops the clock.

    Clock().refreshTime(8)

Syncs the clock with UTC time.(Needs network connection)

    # available fields
    # 'all','year','month','day','week','hour','minute','second'

    value=Clock().getTime(field)

Returns a value from the clock module.

## Ultrasonic Sensor
    
    # available pins
    # 'P0','P1','P2','P3','P8','P9','P12','P13','P14','P15','P16'

    value=MeowSonar(pin).ping()

Returns the distance measured by the ultrasound sensor.

- pin: The pin connected to the sensor.

## RFID Module

    RFID().probe() #without callback
    RFID().probe(probeCallback if 'probeCallback' in dir() else None) #with callback

Starts the scan for RFID tag.

    RFID().stop()

Stops the RFID scanning.

    RFID().uuid()

Returns the RFID UUID.

    RFID().write(BLOCK, SECTOR, DATA)
    RFID().read(BLOCK, SECTOR)

Writes or read the data from the RFID tag.

- BLOCK: RFID block, 1~16.
- SECTOR: RFID sector, 0~2.
- DATA: The data to be written.

## Colour and Gesture Module

    # available type
    # 1,2,3,4

    ColorGes().mode(type)

Sets the mode for the Colour and Gesture Module.

- type: mode
    - Colour Mode: 1
    - Distance Mode: 2
    - Gesture Mode: 3
    - LED Mode: 4
  

    hue = ColorGes().read(0)
    brightness = ColorGes().read(1)

Returns the colour values, hue and brightness, when mode is set to colour.

    distance = ColorGes().distance()

Returns the distance when mode is set to distance. Value ranges from 0 to 255.

    gesture = ColorGes().gesture()

Returns the last gesture when mode is set to gesture.

    ColorGes().ledpwm(0) #LED Brightness
    ColorGes().led((0,0,0,0)) #LED State

Sets the LED brightness and state when mode is set to LED.

- LED Brightness: 0~100
- LED State: 0 for off, 1 for on

## MP3 Module

    # available commands
    # MP3().PLAY, MP3().STOP, MP3().NEXT, MP3().PREV

    MP3().operate(op)

Sends the command to the MP3 module.

- op: Command to send
    - MP3 play: MP3().PLAY
    - MP3 stop: MP3().STOP
    - MP3 next song: MP3().NEXT
    - MP3 previous song: MP3().PREV
  

    MP3().vol(volume) 

Sets the volume for the MP3 player. (0~30)

    MP3().playIndex(index) 

Specify the song to play by index. (The index on the SD card)

    MP3().playName(name) 

Specify the song to play by file name. (Cannot be more than 8 characters)

## Environment Module(Powerbrick)

    # available pin
    # 'P0','P1','P2','P3','P4','P5','P6','P7','P8','P9','P10','P11','P12','P13','P14','P15','P16'

    dht11 = DHT11(pin)

Creates a DHT11 object.

- pin: The pin connected to the sensor.

    dht11.measure()

Asks the sensor to measure environment data.

    temperature = dht11.temperature()
    humidity = dht11.humidity()

Returns the temperature and humidity readings from the sensor.

## Water-proof Temperature Sensor

    # available pins
    # 'P0','P1','P2','P3','P8','P9','P12','P13','P14','P15','P16'

    value=DS18B20(pin).read()

Reurns the temperature reading from the sensor.

- pin: The pin connected to the sensor.

