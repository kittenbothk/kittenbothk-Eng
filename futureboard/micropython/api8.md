# Programming with MicroPython: Network Time Protocol

## Import FutureBoard Library

Import the Library to make use of its functions.

    from future import *
    
## 08:  Network Time Protocol

## Import NTP Library

    from machine import RTC
    import ntptime
    
### 1. Initiate the Real Time Clock

    rtc = RTC()

### 2. Sync with Network Time

    ntptime.settime(zone=8)
    
Parameter zone is for GMT, default is 8.
    
### 3. Get the current time

    rtc.datetime()
    
Returns a list containing the current time, [year, month, day, week, hour, minute, second].

### Sample Program

    #/bin/python
    from future import *
    
    import ntptime
    
    from machine import RTC
    rtc = RTC()
    
    from time import sleep

    wifi.connect(str("wifi"), "password")
    ntptime.settime(int(8))
    screen.sync = 0
    while True:
      screen.fill((0, 0, 0))
      screen.text("Time:",5,10,2,(0, 119, 255))
      screen.text(str(rtc.datetime()[int(4)])+str(str(":")+str(rtc.datetime()[int(5)])),5,40,3,(0, 119, 255))
      screen.refresh()
      sleep(1)

