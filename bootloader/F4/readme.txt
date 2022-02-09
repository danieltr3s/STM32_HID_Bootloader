To burn the bootloader into the chip:

 - The tools will be in Arduino's hardware folder (dfu-util and stm32flash).
 - The chip must be at, at least, 25ºC, otherwise it won't allow the bootloader to be flashed.
 - There are 3 methods to flash the bootloader:
    - with STM Loader Demonstrator (download from stm website)
	- connect the FTDI to PA9 and PA10, VCC and GND
	- Select the daniel_hid_bootloader.hex and upload.
	or
	- with the stm32flash (Arduino hardware folder in documents)
	- .\stm32flash.exe -g 0x8000000 -b 115200 -w "daniel_hid_bootloader.hex" COM6
	or
	- with the dfu-util (Arduino hardware folder in documents) * NOT TESTED
	- dfu-util -a 0 -s 0x08000000 -D "daniel_hid_bootloader.hex"
