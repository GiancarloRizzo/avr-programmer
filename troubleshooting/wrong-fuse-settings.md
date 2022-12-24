# Wrong fuse-settings
If you accidentally set fuses like clock-src wrong you cannot programm your mcu without reset this fuses.

In order you set external clock, you have to apply the **osz** of avrisp-programmer to the **xtal1-input** of the mcu!
Then checkout at [conFUSE](https://www.engbedded.com/conffuse/) the default-settings for your devicetype. On bottom of the page copy the arguments for avrdude to reset the fuses.

```bash
# atmega8-example: fuse default-settings
avrdude -c avrisp -p m8 -e -U hfuse:w:0xd9:m -U lfuse:w:0xe1:m
```

