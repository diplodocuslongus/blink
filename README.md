# PlatformIO Arduino Blink


# usage

    $ pio run -e <environment name> -t upload

Ex:

    $ pio run -e uno -t upload

Monitor the serial output with 

    pio device monitor

# added:

sf_mm_nrf52840 (getting a SAM-BA fail error)

For the rp2040, use 'pico'
To upload, unplugg the board, keep press boot while  plugging the boad, then release the button.
Or, while the board is plugged in, press and hold BOOT, momentary press RESET and then release BOOT.
A usb device will appear, note the path to that device and specify it in the corresponding environment.


teensymm
MicroMod teensy processor board.
https://www.sparkfun.com/products/16402?utm_source=platformio.org&utm_medium=docs

https://docs.platformio.org/en/latest/boards/teensy/teensymm.html

https://learn.sparkfun.com/tutorials/micromod-teensy-processor-hookup-guide/all


## add a new board


Edit the platformio.ini and add the board following the exisiting format:


    [env:<environment name, example uno>]
    platform = <platform name, ex. atmelavr>
    board = <board ID, ex. a-star32U4>
    framework = <ex: arduino>

The environment, plaform and board name /ID can be obtained using

    pio boards <name of a board, ex arduino> 

Some boards may require a slight modification to the Blink.cpp (such as the Adafruit feather nrf52840 express) such as adding a header.
The simplest approach is to save the Bink.cpp to a different file and specify the file in the platformio.ini with `build_src_filter`.
Another way would be to add compiler predirective in platformio and a conditional predirective in the Blink.cpp, details about how to do this can be found on the plaformio site.

## build and upload

To build (but not upload) for a given platform, do:

    pio run -e <environment name>

For example:

    pio run -e leonardo

will build the blink example for the leonardo platform.

Note: when running pio run -e <environment> for the first time, the corresponding platform will be installed.

    $ pio run -e teensy41
    Processing teensy41 (platform: teensy; board: teensy41; framework: arduino)
    ---------------------------------------------------------------
    Platform Manager: Installing teensy
    Downloading  [####################################]  100%
    Unpacking  [####################################]  100%
    Platform Manager: teensy @ 4.15.0 has been installed!

And to upload the .hex firmware (and rebuild the source), do:

    pio run -e <environment name> -t upload

As an example for the a-star32U4 board from pololu.

    pio run -e a-star32U4 -t upload

## new boards added:

- a-star32U4 (Pololu)
- adafruit_feather_nrf52840 (should work with any most nrf52840 adafruit boards, but only tested with the express version, Product ID: 4062)


## original readme from blacksetter

*with added notes by diplodocuslongus*

Blink Example For Arduino which builds using PlatformIO and runs on a variety of boards.

Tested boards:

 - Adafruit adafruit_itsybitsy_m4
 - Adafruit trinket_m0
 - Arduino leonardo
 - Arduino micro
 - Arduino nano_33_iot
 - Arduino uno
pio run -e uno -t upload
 - Arduino yun
 - a-star32U4 *
pio run -e a-star32U4 -t upload
 - Attiny84
 - Digispark ATTINY85 digispark-tiny
 - ESP32 esp32thing
 - ESP32 lolin32
 - ESP8266 d1_mini
 - PJRC teensylc
 - PJRC teensy31
 - PJRC teensy36
 - PJRC teensy40
 - PJRC teensy41 https://www.pjrc.com/store/teensy41.html
    $ pio run -e teensy41
 - Sipeed sipeed-longan-nano
 - ST disco_f746ng
 
* added and tested diplodocuslongus
I keep this around as a sanity check for basic testing of boards.
