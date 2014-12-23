This is an integrated environment to develop standalone software for the ESP8266 module.

To get started, 
1) clone this repo
	git clone 
2) add esp8266_environment/xtensa-lx106-elf/bin to your PATH variable
	cd esp8266_environment/xtensa-lx106-elf/bin
	export PATH=$PWD:$PATH
3) Make a copy of the SDK to start working on your project
	cp esp_iot_sdk_v0.9.4 esp_iot_sdk_v0.9.4_IoT -rfv
4) copy the IoT_Demo example to the app directory of SDK
	cd esp8266_environment/esp_iot_sdk_v0.9.4_IoT/app
	cp ../examples/IoT_Demo/* . -rfv
5) compile your App
	./gen_misc.sh
6) Now, flash the new image from  the bin folder
	esptool.py --port /dev/ttyUSB0 write_flash 0x00000 eagle.app.v6.flash.bin 0x40000 eagle.app.v6.irom0text.bin


Sources:

Bits and pieces have been colected from all around, primarily from the official VM

Toolchain is partially based on instructions from https://github.com/esp8266/esp8266-wiki/wiki and finished off from parts extracted from the official VM (https://drive.google.com/folderview?id=0B5bwBE9A5dBXaExvdDExVFNrUXM&usp=sharing)

SDK is esp_iot_sdk_v0.9.4_14_12_19 - from http://bbs.espressif.com/viewtopic.php?f=5&t=90

AT demo v0.20 is based on SDK v0.9.3 from http://bbs.espressif.com/viewtopic.php?f=5&t=64 works only with 9.3 SDK. So an instance of it is also given

esptool.py [from https://github.com/themadinventor/esptool] for uploading images is available in teh compiler bin folder
