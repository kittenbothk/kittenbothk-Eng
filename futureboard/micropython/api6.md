# Programming with MicroPython: NeoPixel

## Import FutureBoard Library

Import the Library to make use of its functions.

    from future import *
    
## 06: Neopixel

### 1. Initiate a NeoPixel Strip

    NeoPixel(pin, num)
    
Initiates a NeoPixel Strip with a number of LEDs on the selected pin.

Use P7 and 3 for the built-in LED Strip.

### 2. Setting Color for 1 LED

    setColor(i, color)
    
Parameter i denotes the id of the LED.

Neopixel accepts RGB value or built-in color names.

### 3. Setting Color for All LED

    setColorAll(color)
    
Neopixel accepts RGB value or built-in color names.

### 4. Update Display

    update()
    
Update the display to show the effects.

### Sample Program

    # Lights up LEDs then turns off
    
    from future import *
    import time
    """ Available colours
    RED=(255,0,0)
    YELLOW=(255,255,0)
    PINK=(255,105,180)
    WHITE=(255,255,255)
    BLACK=(0,0,0)
    GREEN=(0,255,0)
    BLUE=(0,0,255)
    PURPLE=(148,0,211)
    CYAN = (0,255,255) 
    """
    np = NeoPixel('P7', 3)
    color = [RED,GREEN,BLUE]
    for i in range(3):
        np.setColorAll(color[i])
        np.update() #Update display
        time.sleep(1)
    for i in range(3):
        np.setColor(i,BLACK)
        np.update() #Update display
        time.sleep(1)