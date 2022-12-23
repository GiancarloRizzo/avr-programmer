# Inappropriate ioctl for device

```bash
avrdude -p m8 -c avrispv2 -F
#...
# avrdude: ser_open(): can't set attributes for device "/dev/ttyS0": Inappropriate ioctl for device
```

Error is thrown because 
- you have choosen wrong programmer, e.g. avrispv2 instead of avrisp2
- or you have choosen wrong interface via `avrdude -P /dev/ttyxxx ...`

