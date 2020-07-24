# blink example

blink blue led example for ESP8266 (like this example: https://www.youtube.com/watch?v=cf6QGyYoVPY&t=67s by Prof. Andrea Pollini, but with eclipse and esp8266)

install ESP8266_RTOS_SDK and tools (guide at: https://docs.espressif.com/projects/esp8266-rtos-sdk/en/latest/get-started/)

then:

    git clone git@github.com:Esp8266-IoT/blink.git
    make clean
    make all
  
connect your board and

    make flash
    make monitor

this is an example of build

    make all
    
    Toolchain path: /hd/esp/xtensa-lx106-elf/bin/xtensa-lx106-elf-gcc
    Toolchain version: crosstool-ng-1.22.0-100-ge567ec7
    Compiler version: 5.2.0
    Python requirements from /hd/esp/ESP8266_RTOS_SDK/requirements.txt are satisfied.
    App "blink" version: 25c1c99
    CC build/app_update/esp_app_desc.o
    AR build/app_update/libapp_update.a
    Generating esp8266.project.ld
    LD build/blink.elf
    esptool.py v2.4.0
    To flash all build output, run 'make flash' or:
    python /hd/esp/ESP8266_RTOS_SDK/components/esptool_py/esptool/esptool.py --chip esp8266 --port /dev/ttyUSB0 --baud 115200 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 40m --flash_size 4MB 0x0 /hd/eclipse-cpp-2018-12/eclipse/workspace/blink/build/bootloader/bootloader.bin 0x10000 /hd/eclipse-cpp-2018-12/eclipse/workspace/blink/build/blink.bin 0x8000 /hd/eclipse-cpp-2018-12/eclipse/workspace/blink/build/partitions_singleapp.bin

this is an example of monitor

    make monitor

    I (45) boot: ESP-IDF v3.2-489-g1f5bed1-dirty 2nd stage bootloader
    I (46) boot: compile time 07:33:31
    I (46) qio_mode: Enabling default flash chip QIO
    I (51) boot: SPI Speed      : 40MHz
    I (55) boot: SPI Mode       : QIO
    I (59) boot: SPI Flash Size : 4MB
    I (63) boot: Partition Table:
    I (67) boot: ## Label            Usage          Type ST Offset   Length
    I (74) boot:  0 nvs              WiFi data        01 02 00009000 00006000
    I (82) boot:  1 phy_init         RF data          01 01 0000f000 00001000
    I (89) boot:  2 factory          factory app      00 00 00010000 000f0000
    I (97) boot: End of partition table
    I (101) esp_image: segment 0: paddr=0x00010010 vaddr=0x40210010 size=0x182ec ( 99052) map
    0x40210010: _stext at ??:?

    I (143) esp_image: segment 1: paddr=0x00028304 vaddr=0x402282fc size=0x03f10 ( 16144) map
    I (148) esp_image: segment 2: paddr=0x0002c21c vaddr=0x3ffe8000 size=0x003c8 (   968) load
    I (150) esp_image: segment 3: paddr=0x0002c5ec vaddr=0x40100000 size=0x00a50 (  2640) load
    I (159) esp_image: segment 4: paddr=0x0002d044 vaddr=0x40100a50 size=0x04bb4 ( 19380) load
    I (174) boot: Loaded app from partition at offset 0x10000
    I (189) system_api: Base MAC address is not set, read default base MAC address from EFUSE
    I (194) system_api: Base MAC address is not set, read default base MAC address from EFUSE
    phy_version: 1159.0, 85b471e, Apr 21 2020, 17:03:08, RTOS new
    I (257) phy_init: phy ver: 1159_0
    I (259) reset_reason: RTC reset 1 wakeup 0 store 0, reason is 1
    I (263) APP: Blink Application Stated
    I (266) APP: This is ESP8266 chip with 1 CPU cores, WiFi,
    I (272) APP: silicon revision 1, 
    I (276) APP: 4MB external flash

    I (280) gpio: GPIO[2]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0 
    I (289) APP: Blinking ...
    I (2291) APP: Blinking ...
    I (4292) APP: Blinking ...
    I (6292) APP: Blinking ...
    I (8293) APP: Blinking ...
