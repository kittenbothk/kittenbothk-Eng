# RC Kart

![](../images/car.jpg)

Control the kart using a Joystick sensor or via an IoT platform.

## Building Instructions

[Building Instructions(Right Click->Save As)](https://github.com/kittenbothk/kittenbothk/raw/master/Kits/future_inventor/instructions/pdf/rc_kart.pdf)

## Sample Wiring Diagram

![](../images/rc_kart_wire.png)
## Sample Program

### KittenBlock Sample Program

![](../images/rc_kart_code.png)

[Download Sample Program(Right Click->Save As)](https://github.com/kittenbothk/kittenbothk/raw/master/Kits/future_inventor/instructions/sb3/rc%20kart.sb3)

### Python參考程式

    #/bin/python
    
    from time import sleep
    from future import *
    from sugar import *
    import robotbit

    x = 0
    y = 0
    
    
    def indicator():
      global x,y
    
      if Joystick().value('x') > 50:
        neopix.setColor(2, (255, 255, 0))
        neopix.update()
        sleep(0.1)
        neopix.setColorAll((0,0,0))
      if Joystick().value('x') < -50:
        neopix.setColor(0, (255, 255, 0))
        neopix.update()
        sleep(0.1)
        neopix.setColorAll((0,0,0))
    
    
    
    def valmap(x, in_min, in_max, out_min, out_max):
        return int((x-in_min) * (out_max-out_min) / (in_max-in_min) + out_min)
    
    
    robot = robotbit.RobotBit()
    
    robot.geekServo2kg(1, 90)
    
    neopix=NeoPixel("P7",3)
    
    while True:
      robot.geekServo2kg(1, valmap(Joystick().value('x'), 100, -100, 110, 80))
      robot.motor(1,valmap(Joystick().value('y'), -255, 255, 60, -60))
      indicator()

[Download Sample Program(Right Click->Save As)](https://github.com/kittenbothk/kittenbothk/raw/master/Kits/future_inventor/instructions/py/kart.py)

## Program Instructions

Push the joystick to control the rc kart. The indicators will light up when steering.