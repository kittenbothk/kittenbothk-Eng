# Sugar Light Sensor Module

![](./images/light1.png)

This is a light sensor module in the Sugar sensor series, the pin holes on the back allow compatibility with plastic building bricks.

## Product Specifications

- Dimensions: 24 x 24 x 23 mm
- Weight: 6.7g
- Type: Analog

## Wiring

Use a 3Pin cable to connect 

![](./images/light_wire.png)

## Programming Tutorial

## MakeCode Programming Tutorial

![](../PWmodules/images/mcbanner.png)

### Import Sugar Extension

### Search for sugar in the search bar (Kittenbot products has been verified by Microsoft)

![](./images/sugar_search.png)

### Extension URL

Sugar extension: https://github.com/KittenBot/pxt-sugar

### [Importing Extensions](../../Makecode/powerBrickMC)

![](./images/light_mc_code.png)

[Sample Program](https://makecode.microbit.org/_2fHAo4aYLTy0)

### Kittenblock Programming Tutorial

![](../PWmodules/images/kbbanner.png)

![](./images/light3.png)

### MicroPython Programming

    Light(pin)
    value()

- value(): Analog Value

Sample Program

    from future import *
    
    from sugar import *
    
    light_P0 = Light('P0')
    
    x = 0
    
    screen.sync = 0
    while True:
      screen.fill((0, 0, 0))
      screen.text(light_P0.value(),5,10,2,(0, 119, 255))
      screen.refresh()


