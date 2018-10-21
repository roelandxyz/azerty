The Apple azerty and Windows azerty (Belgium period) layouts are a bit different.  
This layout is a combination to make them both work.  
It is also more developer friendly.

# Screenshot

![Layout](/keyboard-layout.png)

# Installing on macOS

-   sudo cp -r AzertyR03.bundle /Library/Keyboard\ Layouts/
-   reboot
-   select new layout from keyboard settings -> input sources

Here some extra information:  
http://apple.stackexchange.com/questions/43845/how-do-i-type-a-%C2%B2-or-a-%C2%B3-on-an-apple-keyboard-international-english-layout/45402#45402

If you need to re-identify your keyboard for some reason:  
sudo rm /Library/Preferences/com.apple.keyboardtype.plist

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
Tested with Gnome 3.26 on Ubuntu 17.10 / Xfce 4.12 on Arch (Manjaro) / Kubuntu 18.10

Here is some more information: https://askubuntu.com/questions/973659/custom-keyboard-variant-not-selectable

I also switched home/end and pgdn/pgup, but that is only because of my current laptop keyboard layout.  
Here is the config if you need it:

    key <HOME> {	[  Prior	]	};
    key <PGUP> {	[  Home		]	};
    key  <END> {	[  Next		]	};
    key <PGDN> {	[  End		]	};
