The Apple azerty and Windows azerty (Belgium period) layouts are a bit different.  
This layout is a combination to make them both work.  


Installing on macOS
===================
- sudo cp -r AzertyR03.bundle /Library/Keyboard\ Layouts/  
- reboot  
- select new layout from keyboard settings -> input sources  

Here some extra information:  
http://apple.stackexchange.com/questions/43845/how-do-i-type-a-%C2%B2-or-a-%C2%B3-on-an-apple-keyboard-international-english-layout/45402#45402

If you need to re-identify your keyboard for some reason:  
sudo rm /Library/Preferences/com.apple.keyboardtype.plist


The layout is made with [Ukele](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=ukelele)

Installing on Windows
=====================
- Run the setup (check the releases)
- Choose the new layout

The layout and installer is made with [Microsoft Keyboard Layout Creator](https://msdn.microsoft.com/en-us/globalization/keyboardlayouts.aspx)

Screenshots
===========

Normal:  
![Normal](/screenshots/azerty_normal.png)

Shift:  
![Normal](/screenshots/azerty_shift.png)

Option:  
![Normal](/screenshots/azerty_option.png)

Option+Shift:  
![Normal](/screenshots/azerty_option_shift.png)
