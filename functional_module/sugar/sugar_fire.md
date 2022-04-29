# Sugar Flame Sensor Module

![](./images/flame1.png)

This is a flame sensor in the Sugar sensor series. The pin holes on the back allow compatibility with plastic building blocks.

## Product Specifications

- Dimensions: 24 x 24 x 23 mm
- Weight: 6.7g
- Type: Analog Signal

## Wiring

Connect the module to Robotbit Edu with a 3Pin cable.

![](./images/flame_wire.png)

## Programming Tutorial

## MakeCode Programming Tutorial

![](../PWmodules/images/mcbanner.png)

### Import Sugar Extension

### Search for sugar in the search bar (Kittenbot products has been verified by Microsoft)

![](./images/sugar_search.png)

### Extension URL

Sugar extension: https://github.com/KittenBot/pxt-sugar

### [Importing Extensions](../../Makecode/powerBrickMC)

![](./images/flame_mc_code.png)

[Sample Program](https://makecode.microbit.org/_K7dMPuETch1M)

### Kittenblock Programming Tutorial

![](./images/flame3.png)

### MicroPython Programming Tutorial

    Flame(pin)
    value()

- value(): Returns the analog reading

Sample Program

    from future import *
    
    from sugar import *
    
    flame_P0 = Flame('P0')
    
    x = 0
    
    screen.sync = 0
    while True:
      screen.fill((0, 0, 0))
      screen.text(flame_P0.value(),5,10,2,(0, 119, 255))
      screen.refresh()

