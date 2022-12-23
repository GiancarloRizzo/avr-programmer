# invalid signature failure
check if signature is correct. If you got something like this:
```bash
avrdude -p m8 -c avrisp2 -F

#avrdude: stk500v2_command(): command failed
#avrdude: stk500v2_program_enable(): bad AVRISPmkII connection status: Unknown status 0x00
#avrdude: initialization failed, rc=-1
#avrdude: AVR device initialized and ready to accept instructions
#avrdude: Device signature = 0x4020de
#avrdude: Expected signature for ATmega8 is 1E 93 07
```

you've overwritten internal fuses and you have to reset them like discribed in this (blogpost)[]
