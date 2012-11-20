htc-vision-extended-keymap
==========================

An extended keymap for the qwertz hardware keyboard of my HTC Vision (aka G2, Desire Z).

Cyanogenmod 7.2.0
-----------------

If you use CM7.2 and your HTC Vision has a german qwertz keyboard this extended keymap is for you.

### Additional assignments

	USR1        => \      |      /
	USR2        => [      {      <
	USR3        => ]      }      >
	AT          =>               ^
	COMMA       =>               ~

USR1 is the left softkey (labeled as SYM).
USR2 is the first right softkey (labeled as :.1).
USR3 is the second right softkey (labeled as :.2).


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

