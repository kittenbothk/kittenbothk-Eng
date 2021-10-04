# Programming with MicroPython: Robotbit

## Import FutureBoard Library

Import the Library to make use of its functions.

    from future import *
    
## 11: RobotBit

## Import Robotbit Library

    import robotbit
    
### 1. Initiate a Robotbit Object

    rb=robotbit.RobotBit()
    
### 2. Motor Speed

    rb.motor(index,speed)
    
Parameter index indicates the port of motor, value range is 1~4.
Parameter speed controls the speed, value range is -255~255.

### 3. Stop All Motors

    rb.motorStopAll()
    
### 4. Control Servos

    rb.servo(index,degree)
    
Parameter index indicates the servo port, value range is S1~S8.
Parameter angle controls the angle, value range is 0~180.

### 5. Control GeekServo 9G Servos

    rb.geekServo9g(index,degree)
    
Parameter index indicates the servo port, value range is S1~S8.
Parameter angle controls the angle, value range is -45~225.

### 6. Control GeekServo 2K Servos

    rb.geekServo2kg(index,degree)
    
Parameter index indicates the servo port, value range is S1~S8.
Parameter angle controls the angle, value range is 0~360.

### 7. Twin Stepper Motors

    rb.stepperDual(degree1,degree2)
    
    Parameters degree1 and degree2 control M1 and M2 respectively.
    
### 8. Single Stepper Motor

    rb.stepperDegree(index,degree)
    
Use index to select the motor port, value range is 1~2.
Parameter degree controls the angle.