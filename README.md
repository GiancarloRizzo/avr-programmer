# test-setup: atmega8 programming via [avrisp-programmer all-avr](http://avr-programmer.com/all-avr/)

## pre
```bash
sudo apt install avrdude avr-gcc -y
```

## wiring
- connect necessary pins from 6-pin or 10-pin male-header according to the pinout in the according pdf
- make sure you set the jumpers correct. check [all-avr.pdf](https://github.com/GiancarloRizzo/avr-programmer/blob/master/all-avr_installation_de_en.pdf)

## programming-example for atmega8

```bash
### check if programmer is available
lsusb 
#...


### check if connection to µc is successfull
avrdude -c avrisp2 -p m8 
# ... should show:
# Reading | ################################################## | 100% 0.00s
# avrdude: Device signature = 0x1e9307 (probably m8)
# avrdude: safemode: Fuses OK (E:FF, H:D9, L:E1)

# if device-signature is not correct make sure you're using correct µc or to make sure you did not changed src-clock-frequency like discribed in this [blog-post](check https://www.kollino.de/arduino/yikes-invalid-device-signature-da-brennen-mir-die-sicherungen-durch/)


### check if flashing code to µc would be successfull via -n flag.
avrdude -c avrisp2 -p  m8 -n  -e -U flash:w:atmega8xxx/src/blink.hex


### if it success run:
avrdude -c avrisp2 -p  m8 -e -U flash:w:atmega8xxx/src/blink.hex
```

## links
- [http://avr-programmer.com/](http://avr-programmer.com/)
- [https://www.kollino.de/arduino/yikes-invalid-device-signature-da-brennen-mir-die-sicherungen-durch/](https://www.kollino.de/arduino/yikes-invalid-device-signature-da-brennen-mir-die-sicherungen-durch/)

