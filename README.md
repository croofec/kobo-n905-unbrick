For unbrick, you need a connection with uart and sdcard.

For uart:

![](https://raw.githubusercontent.com/croofec/kobo-n905-unbrick/main/screens/screen0.jpg)

For the preparation of the card you can use the latest firmware from [link](https://pgaskin.net/KoboStuff/kobofirmware.html) (Kobo Touch A/B) or you can use [link](https://github.com/croofec/kobo-n905-unbrick/raw/main/kernel/uImage).

for Linux (or for windows use to some image tool)

`dd if=./uImage of=/dev/disk2 bs=512`

after that put sdcard into the slot.

The first goal is to interrupt the kernel boot process. For this, you need to shorten the MMC line to the ground.

More or less place of this line

![](https://raw.githubusercontent.com/croofec/kobo-n905-unbrick/main/screens/screen001.jpg)

and the line under the microscope (it’s some data line for MMC - I don’t know which one)

![](https://raw.githubusercontent.com/croofec/kobo-n905-unbrick/main/screens/screen1.jpg)



you need to do it after start booting but before the kernel load (try a reset, short to ground for success). If you succeed you’ll see the prompt:

![](https://raw.githubusercontent.com/croofec/kobo-n905-unbrick/main/screens/screen2.png)

then just change boot delay:

![](https://raw.githubusercontent.com/croofec/kobo-n905-unbrick/main/screens/screen3.png)



after that let’s try recovery your kobo:

![](https://raw.githubusercontent.com/croofec/kobo-n905-unbrick/main/screens/screen4.png)

The first-line disabled quite mode for kernel, the second read kernel from your sdcard and run recovery mode.

now just run

![](https://raw.githubusercontent.com/croofec/kobo-n905-unbrick/main/screens/screen5.png)

after that, you will see a lot of debugging information from the kernel and blinking blue led on the kobo device.

Restart and enjoy!

![](https://raw.githubusercontent.com/croofec/kobo-n905-unbrick/main/screens/screen6.jpg)


After that of course you need to hack again kobo for custom installation.
