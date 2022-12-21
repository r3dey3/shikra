# Shikra Docs and programming

This started as a fork of the shikra programming repo, and then I added 
the documentation I was able to find on archive.org. The product page and
blog describing the usage is no longer live, so I created this repo.

Extra Pinout Information; the shikra is essentially a FT232H breakout board
* pins 1-7 are ADBUS0-7
* pins 8-16 are ACBUS0-7 (pin 14 has a resister in series between ACBUS5 and pin)
* ping 17 is a 500mA fused controllable 5V supply with ACBUS8 (I think)
* ACBUS9 connected to is a LED (low to turn on)



Adafruit has some good documentation about their FT232H breakout that can be used
- https://learn.adafruit.com/adafruit-ft232h-breakout

## Common UART Pins
* 1 - TX
* 2 - RX
* 3 - RTS
* 4 - CTS
* 5 - DTR
* 6 - DSR
* 7 - DCD
* 18 - GND

## JTAG Pins
* 1 - TCK
* 2 - TDI
* 3 - TDO
* 4 - TMS
* 18 - GND

## SPI Pins
* 1 - SCK
* 2 - SDI
* 3 - SDO
* 4 - CS
* 18 - GND

---
# Original Readme

# Shikra EEPROM Programming

## Requirements

1. Install Libusb: `sudo apt-get install libusb-dev` on linux. OSX can skip this step.
2. Install pyusb python libusb bindings: `sudo pip install pyusb`
3. Run Shikra programming utility: `sudo ./shikra.py` Root access is needed to be able to Read and Write to the Shikra USB Device.

## Using LED programming methods

The Shikra programming utility allows users to enable the Shikra LED under different configurations. These methods are called `set_led_*`
Warning: This may not work with older Shikra devices.

1. Run utility: `sudo ./shikra.py`
2. Find attached Shikra device with `find_shikra`
3. Set LED configuration with `set_led_*`
4. Write config to Shikra EEPROM with `write_config`

## Utility Output

```
[+] Welcome to the SHIKRA programming utility by XIPITER.

  ###### ###  ##  ###  ###  ##  ######      ####
 ###  ## ###  ##  ###  ### ##   ###  ##    #####
 ####    ###  ##  ###  #####    ###  ##   ## ###
  #####  #######  ###  #####    ######   ##  ###
    #### ###  ##  ###  ### ##   ### ##  ########
 ##  ### ###  ##  ###  ###  ##  ###  ## ##   ###
  #####  ###  ##  ###  ###  ##  ###  ## ##   ###

shikra> help

Documented commands (type help <topic>):
========================================
find_shikra  help

Undocumented commands:
======================
EOF  exit

shikra> find_shikra
[+] Looking for Shikra...
[+] Shikra device found.
shikra programming> help

Documented commands (type help <topic>):
========================================
backup         help                 set_led_off  set_led_tx    zero
dump           print_config         set_led_on   set_led_txrx
factory_reset  restore_from_backup  set_led_rx   write_config

Undocumented commands:
======================
EOF  exit

shikra programming>
```
