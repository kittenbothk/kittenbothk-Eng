# Robotbit Coding with KittenBlock

Robotbit can be programmed with KittenBlock.

Refer to this page for introduction with Kittenblock: [Kittenblock Introduction](../KittenBlock/index)

## Kittenblock Coding

![](../../functional_module/PWmodules/images/kbbanner.png)

Connect the Micro:bit to your computer with a USB cable.

Click select hardware and choose MicroBit Python from the menu.

![](../RBimage/add.png)

Press this exclamation mark(!).

![](../../functional_module/PWmodules/kbimages/kbmbcon.png)

Click this button to connect the Micro:bit.

![](../../functional_module/PWmodules/kbimages/kbmbcon1.png)

![](../../functional_module/PWmodules/kbimages/kbmbcon2.png)

Micro:bit will display a heart icon after connecting to Kittenblock.

If the Micro:bit does not show a heart icon, 

![](../../functional_module/PWmodules/kbimages/upload.png)

#### The blocks for Robotbit will be added

![](../RBimage/success1.png)

### 1. Programming Motors

![](../RBimage/robotbit_motorKB.png)

For information about DC motors by Kittenbot, please visit: [Kittenbot Actuators](../../motors/index)

#### Sample Program:

Connect 2 DC motors to the M1A and M1B port of the Robotbit.

![](../RBimage/motor_wire.png)

    The speed of motor ranges from -255 to 255.

![](../RBimage/kb_code1.png)

### 2. Programming Servos

For information about servos by Kittenbot, please visit: [Kittenbot Actuators](../../motors/index)

#### Sample Program:

Connect a servo to the S1 port of Robotbit.

    Connect the orange wire from the servo to the yellow wire of the Robotbit.

![](../RBimage/servo_wire.png)

    Typical servos have a rotation range of 0-180.
    
![](../RBimage/kb_code2.png)

### 3. Programming Stepper Motors

For information about DC motors by Kittenbot, please visit: [Kittenbot Actuators](../../motors/index)

#### Sample Program:

Connect Stepper Motors to the M1 and M2 port of the Robotbit, with the red wire connecting to the VM port.

![](../RBimage/stepper_wire.png)

    Stepper Motors have a rotation range of -360 to 360.

![](../RBimage/kb_code3.png)

### 4. Programming the buzzer

Do not remove the buzzer jumper when using the buzzer.

![](../RBimage/kb_code4.png)

### 5. Programming the built-in LED strip

    Remember to add a "Show" block to display the effect.

#### 5.1 Lighting up all lights

![](../RBimage/kb_code5.png)

#### 5.2 Customizing color with RGB

    RGB value has a range of 0-255.

![](../RBimage/kb_code6.png)

#### 5.3 Lighting up individual lights

    The lights are labelled 0-3. (As labelled on the Robotbit)
    
![](../RBimage/robotbit_neopixel2.png)

![](../RBimage/kb_code7.png)

### 6. Programming the IO Pins

The blocks for the IO pins are found in the menu for Micro:bit.

![](../RBimage/robobit_pinKB.png)

    Pin 0-2 can be used as analog pins while P8, P12~P15 can only be used as digital pins.
    Analog values have a range of 0 to 1023, digital values have a range of 0 to 1.
    
![](../RBimage/robobit_pinKB1.png)

#### 6.1 Reading values from pins

    Pin 0 is occupied by the buzzer by default, the jumper should be removed when using this pin.

![](../RBimage/robobit_pinKB2.png)

#### 6.2 Writing values to pins

    Pin 0 is occupied by the buzzer by default, the jumper should be removed when using this pin.

![](../RBimage/robobit_pinKB3.png)