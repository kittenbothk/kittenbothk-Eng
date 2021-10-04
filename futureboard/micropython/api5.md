# Programming with MicroPython: GPIO

## Import FutureBoard Library

Import the Library to make use of its functions.

    from future import *
    
## 05: GPIO

### 1. Initiate Pin Mode

    MeowPin(pin,mode)
    
Initiates the GPIO with a mode, use P1~P16 for parameter pin.

Possible values for parameter mode:
1. Digital Input: 'IN'
2. Digital Output: 'OUT' 
3. Analog Input: 'ANALOG'  
4. Analog Output: 'PWM'

### 2. Read a Digital Value

    getDigital() 

### Sample Program

    from future import *
    # Digital Read Pins=['P0','P1','P2','P3','P8','P9','P12','P13','P14','P15','P16']
    p0 = MeowPin('P0','IN')
    print(p0.getDigital())

### 3. Write a Digital Value

    setDigital(val)
    
### Sample Program

    from future import *
    import time
    # Digital Write Pins=['P0','P1','P2','P6','P7','P8','P10','P13','P3','P9','P14','P15','P16']
    p0 = MeowPin('P0','OUT')
    while 1:
        p0.setDigital(1)
        time.sleep(1)
        p0.setDigital(0)
        time.sleep(1)
        
### 4. Read an Analog Value

    getAnalog(width)
    
FutureBoard has a 12-bit ADC, use 10 for 10-bit values and 12 for 12-bit values, default is 12.

### Sample Program

    from future import *
    # Analog Read Pins=['P0','P1','P4','P12', 'P3', 'P14', 'P15', 'P16']
    
    p0 = MeowPin('P0','ANALOG')
    print(p0.getAnalog())
    print(p0.getAnalog(width=10))
    
### 5. Write an Analog Value

    setAnalog(val)

### Sample Program
    
    from future import *
    import time
    # Analog Write Pins=['P0','P1','P2','P3','P8','P13','P14','P15','P16']
    
    p0 = MeowPin('P0','PWM')
    while 1:
        for i in range(1023): 
            p0.setAnalog(i)
            time.sleep_ms(1)
        for i in range(1023,0,-1): 
            p0.setAnalog(i)
            time.sleep_ms(1)
            
