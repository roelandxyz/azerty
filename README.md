A better azerty for Developers.

# Most important changes

- The top left key is for @ and # (like Apple does, but now also for Windows/Linux)
- { and } are placed next to enter and are now easy to use. (see screenshot)

# Screenshot

![Layout](/keyboard-layout.png)

# Installing on macOS

1. Copy the `.keylayout` file to the `Keyboard Layouts` folder within `/Library`. In command form:

	```bash
	# Install the keyboard layout system-wide
	cd /Library/Keyboard\ Layouts; sudo curl -O# https://raw.githubusercontent.com/r03/azerty/master/mac/r03.keylayout
	```

2. Reboot, or log out and log in again.

3. Enable the new keyboard layout via _System Preferences_ › _Keyboard_ › _Input Sources_ › _AZERTY_.

### How to make the custom keyboard layout the system default

To use the custom layout for the login screen, you need to [set it as the system default](http://apple.stackexchange.com/a/108836/4408).

1. Run the following command:

	```bash
	sudo curl -#o /Library/Preferences/com.apple.HIToolbox.plist https://raw.githubusercontent.com/r03/azerty/master/mac/tmp.plist
	```

2. Reboot.


[original installation instructions](https://raw.githubusercontent.com/mathiasbynens/custom.keylayout/master/azerty/README.md)

The layout is made with [Ukele](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=ukelele)

# Installing on Windows

-   Run the setup (check the releases)
-   Choose the new layout

The layout and installer is made with [Microsoft Keyboard Layout Creator](https://msdn.microsoft.com/en-us/globalization/keyboardlayouts.aspx)

# Installing on Linux

Add this to the end of file `/usr/share/X11/xkb/symbols/be`:

    partial alphanumeric_keys
    xkb_symbols "r03" {

        include "be(basic)"
        name[Group1]="Belgian (r03)";

        key <TLDE>  { [        at,    numbersign,       notsign,       notsign ] };
        key <AE02>  { [    eacute,             2,            at,   twosuperior ] };
        key <AE03>  { [  quotedbl,             3,    numbersign, threesuperior ] };
        key <AE05>  { [ parenleft,             5,     braceleft,   bracketleft ] };
        key <AE06>  { [parenright,             6,   asciicircum,   fiveeighths ] };
        key <AE10>  { [ parenleft,             0,    braceright,        degree ] };
        key <AE11>  { [parenright,        degree,    braceright,  bracketright ] };

        key <AD11>  { [asciicircum,dead_diaeresis,  bracketleft,dead_abovering ] };
        key <AD12>  { [    dollar,      asterisk,  bracketright,   dead_macron ] };

        key <AC11>  { [ braceleft,       percent,    dead_acute,    dead_caron ] };
        key <BKSL>  { [braceright,      sterling,    dead_grave,    dead_breve ] };

        key <AC09>  { [         l,             L,       lstroke,           bar ] };
        key <AB06>  { [         n,             N,    asciitilde,             N ] };
        key <AB07>  { [     comma,      question,  dead_cedilla,     masculine ] };
        key <AB08>  { [ semicolon,        period,horizconnector,      multiply ] };
        key <AB09>  { [     colon,         slash,periodcentered,     backslash ] };
        key <AB10>  { [     equal,          plus,    asciitilde,  dead_abovedot] };

        key <LSGT>  { [      less,       greater,     backslash,     backslash ] };
    };

Add the new variant to the belgian layout in `/usr/share/X11/xkb/rules/evdev.xml`:

    <variant>
      <configItem>
        <name>r03</name>
        <description>Belgian (r03)</description>
      </configItem>
    </variant>

After a reboot you can select the new layout.
Tested with Gnome 3.26 on Ubuntu 17.10 / Xfce 4.12 on Arch (Manjaro) / Kubuntu 18.10 / Fedora 31

Here is some more information: https://askubuntu.com/questions/973659/custom-keyboard-variant-not-selectable

