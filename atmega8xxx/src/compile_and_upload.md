# compile & and upload

```bash
# create .elf
avr-gcc -mmcu=atmega8 -Wall -Os -o blink.elf blink.c
# create hex
avr-objcopy -j .text -j .data -O ihex blink.elf blink.hex
# upload
avrdude -p m8 -c avrisp2 -e -U flash:w:blink.hex 
```
