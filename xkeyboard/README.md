XKB Config
==========

custom keyboards for linux based on macbook pro 2013.

## Creating a new keyboard layout

This worked for me on Linux Mint 17 (Ubuntu 14.04) to create a new keyboard. Refer to
these at your own risk.  Don't get stuck with an invalid keyboard layout.

### Find your base kbd_symbols layout

Navigate to `/usr/share/X11/xkb` and open `rules/evdev.xml`.  Now,
identify the keyboard you want to base your layout on.  You can search
by the descriptions in the GUI keyboard preferences.  Within the
`<layout>` tag, you'll find the base layout under the `<configItem>`
tag.  Identify the two char code in the `<name>` tag, most likely
`us`.

Now, open `symbols/us` and this is your base symbol layout.  There are
other files you can edit too but you'll need to make more advanced
config changes, like `rules` and a `keymap`.  In `symbols/us`, the
first `kbd_symbols` definition defines the basic symbol layout,
imported by most of the other `kbd_symbols` definitions.  You'll
notice that the others in this file usually have `include "us(basic)`,
which refer to the symbol filename and the symbol definition name.

### Create a new kbd_symbols file

Now, create a new symbols file with a new country code.
I used `io`.  I keep this in my dotfiles and then copy it in with
sudo.  It might be possible to link it in as well.

Here's the basic config I'm starting out with.  With `include "us"`,
i'm pulling in the `us(basic)` config and then overriding that.

After you're done editing, copy your file to `/usr/share/X11/xkb/symbols/xx`.

```
partial alphanumeric_keys
xkb_symbols "basic" {

    include "us"
    name[Group1]= "Digimon - US";

    // swap symbols and digits
    key <TLDE> {	[     grave,	asciitilde	]	};
    key <AE01> {	[     exclam,      1          ]	};
    key <AE02> {	[     at,          2		]	};
    key <AE03> {	[     numbersign,  3	]	};
    key <AE04> {	[     dollar,      4		]	};
    key <AE05> {	[     percent,     5		]	};
    key <AE06> {	[     asciicircum, 6	]	};
    key <AE07> {	[     ampersand,   7	]	};
    key <AE08> {	[     asterisk,    8	]	};
    key <AE09> {	[     parenleft,   9	]	};
    key <AE10> {	[     parenright,  0	]	};
    key <AE11> {	[     minus,	underscore	]	};
    key <AE12> {	[     equal,	plus		]	};

};
```

### Update evdev.xml to include the new layout

You'll need to update `evdev.xml` to include the new layout and any variants
you want included.

```xml
  </modelList>
  <layoutList>

<!-- add the new layout here -->

    <layout>
      <configItem>
        <name>io</name>
        
        <shortDescription>en</shortDescription>
        <description>Digimon (US)</description>
        <languageList>
          <iso639Id>eng</iso639Id>
        </languageList>
      </configItem>
      
      <!-- add any variant lists here -->
      
    </layout>

<!-- US layout and variants start here-->

    <layout>
      <configItem>
        <name>us</name>
   
```

### Reconfigure xkb-data (Ubuntu only?)

I'm not quite sure if this step is required and, if so, when.  But,
[this article](https://help.ubuntu.com/community/Custom%20keyboard%20layout%20definition)
says it is.  Run `sudo dpkg-reconfigure xkb-data`, so that Ubuntu reconfigures
the changes made to your `/usr/share/X11/xkb` folder.  The version of Linux Mint i'm
using seemed to pick up the changes and insert them in the keyboard preferences
as soon as I saved the file.

### Mac OSX Function & Media Keys

You may need to overwrite the `fnmode` file in order for you function keys to work
with the proper priority.  This is described in more detail on [this S/O question](http://unix.stackexchange.com/questions/121395/on-an-apple-keyboard-under-linux-how-do-i-make-the-function-keys-work-without-t).

```
echo 2 > /sys/module/hid_apple/parameters/fnmode
```

### Guides

- https://help.ubuntu.com/community/Custom%20keyboard%20layout%20definitions
- http://www.x.org/releases/X11R7.6/doc/xorg-docs/input/XKB-Config.html
- https://grahamwideman.wikispaces.com/linux+--+keyboard+configuration,+xkb
- https://www.linux.com/learn/tutorials/769644-hacking-your-linux-keyboard-with-xkb
- https://wiki.archlinux.org/index.php/Keyboard_configuration_in_Xorg
- https://wiki.archlinux.org/index.php/X_KeyBoard_extension#Basic_examples
- http://linux.lsdev.sil.org/wiki/index.php/Building_an_XKB_Keyboard

### Docs

- http://www.charvolant.org/~doug/xkb/html/node5.html
- http://www.charvolant.org/~doug/xkb/html/index.html
- http://www.charvolant.org/~doug/xkb/html/node4.html

### Other Links

[Assign shift level to function keys](http://unix.stackexchange.com/questions/155797/xkb-assign-a-new-shift-level-to-function-keys)

### TODO

- base on us international keyboard
- swap quotes on international keys (diacritics)
    - set up accent keys for random punctuation chars
    - how to set keyboard layouts to be used for specific applications?
        - can swap out keyboard layouts with key combo defined in xkb
- use xev to test config
- aliases to reload keyboard changes
