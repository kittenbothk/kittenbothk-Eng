# Sugar Line Sensor Module

![](./images/line1.png)

This is an infrared line sensor module in the Sugar sensor series. The holes on the back allow compatibility with plastic building bricks.

## Product Specifications

- Dimensions: 24 x 24 x 16 mm
- Weight: 5g
- Type: Digital
- Sensing Range: 1~14mm

## Wiring

Use a 3Pin cable to connect the module to Robotbit Edu.

![](./images/line_wire.png)

## Programming Tutorial

## MakeCode Programming Tutorial

![](../PWmodules/images/mcbanner.png)

### Import Sugar Extension

### Search for sugar in the search bar (Kittenbot products has been verified by Microsoft)

![](./images/sugar_search.png)

### Extension URL

Sugar extension: https://github.com/KittenBot/pxt-sugar

### [Importing Extensions](../../Makecode/powerBrickMC)

![](./images/line_mc_code.png)

[Sample Program](https://makecode.microbit.org/_achdEoCzK8DV)

### Kittenblock Programming Tutorial

![](../PWmodules/images/kbbanner.png)

![](./images/line3.png)

### MicroPython Programming Tutorial

    Tracker(pin)
    value()

- value(): Returns Tracker Status

Sample Program

    from future import *
    from sugar import *
    
    tracker = Tracker('P1')
    
    screen.sync = 0
    while True:
        if tracker.value() == 1:
            screen.fill(0)
        else:
            screen.fill(255)
        screen.refresh()