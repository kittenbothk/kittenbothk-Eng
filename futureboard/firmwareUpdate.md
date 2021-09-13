# Firmware Updates

Kittenbot may periodically release firmware updates for the Futureboard to improve functionality and stability.

## Updating the firmware of Futureboard

Download the firmware flashing tool.

[Flashing Tool Download](https://drive.google.com/file/d/1_M4EzolaJWpYXts_FwUIqH8pZWqy-fye/view?usp=sharing)

Unzip the file.

![](./images/update1.png)

Open flash_download_tool_3.8.5.exe.

![](./images/update2.png)

Choose Factory Mode.

![](./images/update3.png)

Select ESP32 Download Tool.

![](./images/update4.png)

Unlock the UI.

![](./images/update5.png)

Select the firmware file ending with .bin.

![](./images/update6.png)

Make sure the memory address is 0x1000 and the check box is ticked.

![](./images/update7.png)

Select the port where the Futureboard is connected and use a baud rate of 1152000, press start and wait.

![](./images/update8.png)

Press the reset switch on the back of the Futureboard.

![](./images/resetbutton.jpg)

If the Futureboard says a reset is required, please refer to [Futureboard Reset](./reset.md).