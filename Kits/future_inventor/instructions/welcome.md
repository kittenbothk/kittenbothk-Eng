# Welcoming Robot

This robot will greet guests by waving its arm and playing a tune.

![](../images/welcome.jpg)

## Building Instructions

[Building Instructions(Right Click->Save As)](https://github.com/kittenbothk/kittenbothk/raw/master/Kits/future_inventor/instructions/pdf/welcome.pdf)

## Sample Wiring Diagram

![](../images/welcome_wire.png)

## Sample Program

### KittenBlock Sample Program

![](../images/welcome_code.png)

[Download Sample Program(Right Click->Save As)](https://github.com/kittenbothk/kittenbothk/raw/master/Kits/future_inventor/instructions/sb3/welcome.sb3)

### Python Sample Program

    #/bin/python
    
    from time import sleep
    from future import *
    from sugar import *
    import robotbit
    
    x = 0
    y = 0
    
    
    def detect():
      global x,y
    
      if PIR("P0").value():
        if TOFDistance().value() < 300:
          x = TOFDistance().value()
          sleep(1)
          y = TOFDistance().value()
          if x > y:
            welcome()
    
    
    
    def welcome():
      global x,y
    
      buzzer.melody(CORRECT)
      screen.fill((0, 119, 255))
      screen.text("Welcome",30,50,2,(255, 255, 255))
      screen.refresh()
      for count in range(3):
        robot.geekServo2kg(1, 90)
        sleep(0.2)
        robot.geekServo2kg(1, 0)
        sleep(0.2)
      screen.clear()
    
    
    
    robot = robotbit.RobotBit()
    
    robot.geekServo2kg(1, 0)
    
    while True:
      detect()

[Download Sample Program(Right Click->Save As)](https://github.com/kittenbothk/kittenbothk/raw/master/Kits/future_inventor/instructions/py/welcome.py)

## Program Instructions

The robot will welcome guests when they walk by.