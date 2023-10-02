# Arcade-Pico

DIY Makecode Arcade board with RP2040 Pico

Here is what I got after playing Pico with Arcade for a few days. Hope this helped.

## Good news:

* work with both Pico & PicoW
* works well with screen(ST7735 160x128) & btn & speaker
* bootloader in rom, very very safe
* UF2 format supported by bootloader naturally !!! Not require compile bootloader anymore! :stuck_out_tongue:
* Pico is faster, and very cheap about 1.5~4$
* can work with 9341(320x240) in spi mode (with a little laggy)

## Bad news: (my test result)

* CFG_PIN_LED can’t sign to on-board led on PicoW, cause it not be driven by any GPIO directly.
* botton pins need pull-up for steady
* no parallel solution yet, can’t setup parallel screen (bigger screen eg: 9341 )
* WebApp don’t support, device appeared but panic(050) when download directly.
* enter MSD mode first every time to upload game ( holding bootsel btn and re-plug usb cable of Pico)
* can’t transfer serial msg via console.log()
* pin.analogRead() always return 0, whatever the pin config I set.


## How to do:

* update config (once):
    * Download my configuration v01: https://github.com/AqeeAqee/Arcade-Pico/blob/main/Arcade-Rp2040Pico_Aqee_v01.uf2
    * holding bootsel btn and re-plug Pico into usb port of computer.
    * Drag&drop this config file into Pico drive.
* download game:
    * In arcade, choose hardware of R2 (need enabled experience hardwares first in About)
    * Before ready to download game, again, holding bootsel btn and re-plug Pico into usb port of computer.
    * Click download in Arcade and save file in Pico drive.
* Done, have fun!

## Pins connection in this version:


    Buttons:s
    pin  6 : MENU
    pin 10 : LEFT
    pin 11 : RIGHT
    pin 12 : UP
    pin 13 : DOWN
    pin 14 : A
    pin 15 : B

    Screen - ST7735
    pin 16 : MISO (optional)
    pin 17 : CS (or directly to GND)
    pin 18 : SCK
    pin 19 : MOSI
    pin 20 : DC
    pin 21 : RST
    pin 22 : BL (or directly to 3v3)

    speaker 
    pin 7 (and a GND)

Other settings(GPIOs, I2C, SPI, etc) will be added later, I will share here also when updated.

## Further more:
Go https://microsoft.github.io/uf2/patcher/ , to add or edit settings for your board.
