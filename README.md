htc-vision-extended-keymap
==========================

An extended keymap for the qwertz hardware keyboard of my HTC Vision (aka G2, Desire Z).


### Additional assignments
	                              Base   Shift   FN
	Key 217 = BACKSLASH      =>     `      |     \
	Key 184 = LEFT_BRACKET   =>     <      {     [
	Key 185 = RIGHT_BRACKET  =>     >      }     ]
	Key 215 = AT             =>            ^
	Key 51  = COMMA          =>            ~

 * Key 217 is the left softkey (labeled as SEARCH/SYM).
 * Key 184 is the first right softkey (labeled as :.1).
 * Key 185 is the second right softkey (labeled as :.2).



Cyanogenmod 7.2.0
-----------------

If you use CM7.2 and your HTC Vision has a german qwertz keyboard this extended keymap is for you.

### Compatibility

Your phone must use a german keymap. You can check this by

	$ adb shell getprop | grep hw.keyboards.0
	[hw.keyboards.0.devname]: [vision-keypad-ger]

If getprop does not return "vision-keypad-ger" this keymap won't fit.


### Installation instructions

	adb connect 192.168.178.20:5555
	# mount /system read-write
	adb remount
	adb shell cp /system/usr/keychars/vision-keypad-ger.kcm.bin /system/usr/keychars/vision-keypad-ger.kcm.bin.bak
	adb shell cp /system/usr/keylayout/vision-keypad-ger.kl /system/usr/keylayout/vision-keypad-ger.kl.bak
	# push the new keymap
	adb push vision-keypad-ger.kcm.bin /system/usr/keychars/
	adb push vision-keypad-ger.kl /system/usr/keylayout/
	# reboot
	adb reboot

Cyanogenmod 9.1-unofficial
--------------------------

### Compatibility

Unfortunately the verification by getprop does not work anymore.

### Installation instructions

	adb connect 192.168.178.20:5555
	adb push vision-keypad-ger.kl /sdcard/vision-keypad-ger.kl
	adb push vision-keypad-ger.kcm /sdcard/vision-keypad-ger.kcm
	adb shell
	$ su
	$ mount -o rw,remount /system
	$ cd /system/usr
	$ cp keylayout/vision-keypad-ger.kl keylayout/vision-keypad-ger.kl.orig
	$ cp keychars/vision-keypad-ger.kcm keylayout/vision-keypad-ger.kcm.orig
	$ cp /sdcard/vision-keypad-ger.kl keylayout/
	$ chmod 644 keylayout/vision-keypad-ger.kl
	$ cp /sdcard/vision-keypad-ger.kcm keychars/
	$ chmod 644 keychars/vision-keypad-ger.kcm
	$ reboot

