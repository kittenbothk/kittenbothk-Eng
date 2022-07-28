# Sugar Lens FPV Module

![](./images/lens1.jpg)

Sugar Lens is a FPV Camera Module in the Sugar series, it can be used with a receiver such as HMD, Portable Displays or USB Receivers to display the image in real time.

The module has built-in pin holes for plastic building bricks, enabling the module to be easily mounted to robots or remote control cars. The camera can be turned on or off via coding.

## Product Specifications

- Dimensions: 24 x 24 x 32 mm
- Weight: 11g
- Connection Port: 3Pin PH2.0
- Frequency Range: 5300MHz~5900MHz
- Channels: 8 channels in 5 bands
- Supported Receiver: Head Mounted Display Unit, Portable Displays, USB Receiver(for PC or Android)

## Product Showcase

![](./images/lens2.jpg)

![](./images/lens5.jpg)

![](./images/lens6.jpg)

## Wiring Diagram

Connect the module to a Robotbit Edu with a 3Pin cable.

![](./images/lens_wire.png)

## MakeCode Programming Tutorial

![](../PWmodules/images/mcbanner.png)

### Search Robotbit in the extension browser(Robotbit is approved by Microsoft)

![](./images/robotbit_search.gif)

### Extension Github page: https://github.com/kittenbothk/pxt-SensorPlus

### [Adding Extensions](../Makecode/powerBrickMC)

![](./images/lens_code.png)

Use the Micro:bit buttons to turn or off the FPV camera.

[Sample Program](https://makecode.microbit.org/_JMrYPzC3uigE)

## Operation Instructions

On top of the Sugar Lens module, there is a small black button, that button can be used to access the camera's various settings.

### 1. During normal operation, the blue and red LEDs are lit continuously.

![](./images/lens7.jpg)

### 2. Long press the button to access the settings.

![](./images/lens8.gif)

### 3. When the red light is flashing once, the camera is in the channel settings. The number of blue LED flashes corresponds to the channel, e.g., in the following example, the blue LED flashes 3 times, meaning the camera is now in channgel 3. Press the button to change the channel (from 1 to 8).

![](./images/lens9.gif)

### 4. To go to the next setting, long press the button again, when the red LED flashes twice, the camera is now in the band settings. The number of blue LED flashes corresponds to the band, e.g., in the following example, the blue LED flashes once, meaning the camera is now in band A. Press the button to change the band (from A to E).

![](./images/lens10.gif)

### 5. Long press the button again to go to the final setting. When the red LED flashes three times, the camera is now in the video flip settings. The number of blue LED flashes corresponds to the mode, e.g., in the following example, the blue LED flashes once, meaning the video is not flipped. Press the button to change between modes.

![](./images/lens11.gif)

### 6. Long press the button again to exit the settings.

![](./images/lens8.gif)

## Sugar Lens Receivers Details

Several types of receivers are available for Sugar Lens.

### 1. Head Mounted Display Unit

![](./images/lens21.jpg)

#### Product Specifications:

- Screen Size: 4.3 inches
- Resolution: 800*480
- Port: USB Charging
- Battery Life: ~2 hours
- Functions: Automatic Channel Searching, Screen Recording, Adjustable Brightness and Contrast, AV Out

### Usage Instructions

#### Install the antennas

![](./images/lens23.jpg)

#### Turn on the power

![](./images/lens22.png)

#### Press the SearCH button to begin searching for the strongest channel

![](./images/lens24.gif)

#### Press the REC button to begin recording, press again to stop. (SD Card is required)

![](./images/lens25.png)

#### (Advanced) Switch to the next band by pressing the Band+ button

![](./images/lens26.png)

#### (Advanced) Switch to the next channel by pressing the CH+ button

![](./images/lens27.png)

#### (Advanced) Press the Menu button to go to the settings

![](./images/lens28.png)

### 2. Portable Monitor

![](./images/lens12.jpg)

#### Product Specifications

- Screen Size: 5 inches
- Resolution: 800*480
- Port: USB Charging Port
- Battery Life: ~2 hours
- Functions: Automatic Channel Searching, Adjustable Brightness and Contrast, AV Out

### Usage Instructions

#### Install the antenna

![](./images/lens14.jpg)

#### Turn on the power

![](./images/lens16.jpg)

#### Short press the menu key to start channel searching

![](./images/lens17.gif)

#### (Advanced) Press the -(minus) key to change the band

![](./images/lens18.gif)

#### (Advanced) Press the +(plus) key to change the channel

![](./images/lens19.gif)

#### (Advanced) Long press the menu key to enter the settings

![](./images/lens20.jpg)

### 3. USB Receiver

![](./images/lens29.jpg)

#### Product Specifications

- Port: USB
- Function: Displays video feed on PC/Android phone

### Usage Instructions

#### Install the antennas

![](./images/lens30.jpg)

#### Long press any key to begin searching for channel

![](./images/lens35.gif)

#### Press left or right key to fine tune the frequencies

![](./images/lens34.png)

### Using on PC

#### Connect the receiver to the PC using the USB cable

#### Search for "Camera"

![](./images/lens31.png)

#### If there is already a webcam, press this button to switch to the receiver

![](./images/lens32.png)

#### The video feed will be displayed in real time

![](./images/lens33.png)

### Using on Android Phone

#### Download APK

[Download APK(Right Click->Save as)](./images/fuav.apk)

#### Install the APK

#### Connect the receiver to the phone using the USB cable

#### Open Skydroid FPV app

![](./images/lens37.png)

![](./images/lens36.png)

## Sugar Lens and receivers channel reference table

Refer to this graph for the detailed channels and bands guide for the Sugar Lens and receiver.

There are some differences in how the HMD and the portable monitor marks the band, please be careful when using.

    Notice: Please note that Band E(Red) can only be viewed on the portable monitor.

![](./images/lens38.png)