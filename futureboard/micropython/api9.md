# Programming with MicroPython: I2S Microphone

## Import FutureBoard Library

Import the Library to make use of its functions.

    from future import *
    
## 09: I2S Microphone

## Import I2S Library

    import audio
    
### 1. Initiate the Microphone

    au=audio.Audio()
    
### 2. Get Loudness

    au.loudness()
    
Returns the detected loudness, values ranges from 0~4095.

### 3. Voice Recognition

    au.recognize(sec=1,vid=1737)

Voice Recognition requires Internet Connection.

Set the recognition length in seconds with parameter sec, recommended length is 1~3.

4 languages are supported currently, put the code into the vid parameter.

1. 1537: Putonghua
2. 1737: English
3. 1637: Cantonese
4. 1837: Szechuan Dialect

### Sample Program: Loudness

    import time
    import audio
    au = audio.Audio() 
    
    while 1:
      time.sleep(0.1)
      print(au.loudness())
  
### Sample Program

    #/bin/python
    from future import *
    
    import audio
    au = audio.Audio()

    wifi.connect(str("3DJollyFab"), "goodluckjf11b")
    screen.clear()
    screen.text(au.recognize(vid=1737, sec=2),5,10,1,(0, 119, 255))

