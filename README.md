# PlatformIO Arduino Blink


# usage

$ pio run -e uno -t upload

## add a new board


Edit the platformio.ini and add the board following the exisiting format:


    [env:<environment name, example uno>]
    platform = <platform name, ex. atmelavr>
    board = <board ID, ex. a-star32U4>
    framework = <ex: arduino>

The environment, plaform and boad name /ID can be obtained using

    pio boards <name of a boad, ex arduino> 


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

## new board added:

- a-star32U4

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
 - PJRC teensy41
https://www.pjrc.com/store/teensy41.html

 - Sipeed sipeed-longan-nano
 - ST disco_f746ng
 
* added and tested diplodocuslongus
I keep this around as a sanity check for basic testing of boards.
