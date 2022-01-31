win11 wsl-5.10.60.1 have firstly support usbip feature, it can attach usb device to wsl.
The offical post [Connecting USB devices to WSL](https://devblogs.microsoft.com/commandline/connecting-usb-devices-to-wsl/) describe a brief progress, but not specified some details. 
Then I followed [How to connect ESP32 as USB serial device to Linux in WSL2 on Windows 11](https://georgik.rocks/how-to-connect-esp32-as-usb-serial-device-to-linux-in-wsl2-on-windows-11/) joined windows insider program, and get the latest 5.10.60 kernel.
Finally I successfully attach the usb serial to wsl. If some step get error, reboot windows system.
But wsl don't have cp120x driver. 
 
# install cp120x dirver.
kerner aleady have cp120x dirver, but wsl have no modules 
After search, I found i need to enable kernel modules, and [Building your own USB/IP enabled WSL 2 kernel](https://github.com/dorssel/usbipd-win/wiki/WSL-support#building-your-own-usbip-enabled-wsl-2-kernel) have a clear step to reference.

[Figure 10-3. Kernel configuration for USB dongle serial console using make menuconfig](https://tldp.org/HOWTO/Remote-Serial-Console-HOWTO/kernelcompile-25.html)
Device Drivers -> USB support -> USB Serial Converter support -> USB Serial Console device support + USB Generic Serial Driver + USB CP210x family of UART Bridge Controllers

[Cannot open /dev/ttyUSB0: Permission denied](https://github.com/esp8266/source-code-examples/issues/26#issuecomment-706129191)
```bash
sudo su
//type your password
cd /
cd dev
chown username ttyUSB0
```
