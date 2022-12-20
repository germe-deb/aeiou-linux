<!--
SPDX-FileCopyrightText: 2022 debgerme <fossgerme@tuta.io>

SPDX-License-Identifier: Unlicense
-->

# AEIOU for linux

This is an implementation of the AEIOU keyboard layout; the first Spanish optimized keyboard layout ever made.

![aeiou](https://github.com/germe-deb/aeiou-linux/raw/main/aeiouprev.png)

AEIOU doesn't have any linux compatibility by the moment, but I made an implementation for linux with some changes like symbol positions, and a custom 3rd and 4th level.

the most custom part about it is the symbols. It doesn't respect at all any of the original positions, but it only moves the numbers to the second level.

the new symbol positions are the latin american symbols, but now the 1 without shift is ' and at the right of the 0 key there are the exclamation (!) and the question(?), and shifted there are the open exclamation (¡) and the open question (¿).
I don't know how they are called in english, sorry.

in the aeiou's N and S keys, there are in the 3rd level the minus (-) and the plus (+) symbols.

if you have a latin american keyboard, you use linux and want to try AEIOU, you're in luck!

## Installing

* clone this repo.
* copy the `aeiou` file to `/usr/share/X11/xkb/symbols/` directory
* open your text editor and edit the file `/usr/share/X11/xkb/rules/evdev.xml`
      * find the first `<layout>` (it is near the line 1300)
      * add the next piece of xml code to the file:
```
    <layout>
      <configItem>
        <name>aeiou</name>
        <!-- AEIOU keyboard layout -->
        <shortDescription>aeiou</shortDescription>
        <description>AEIOU Latin American</description>
        <languageList>
          <iso639Id>spa</iso639Id>
        </languageList>
      </configItem>
    </layout>
```

      * don't make mistakes here!!!

* restart your session (or reboot your computer)
* go to settings, keyboard, and add the new layout. I will don't detail this step because it depends on what desktop you're using. gnome is pretty straightforward in this case, pantheon too and maybe even kde, but xfce is another story.

That's it. if you made the installation correctly, you have aeiou installed and ready to use.

here is a screenshot of how I have the evdev.xml file

![evdev](https://github.com/germe-deb/aeiou-linux/raw/main/xkbevdev.png)

here is another screenshot, showing that the file aeiou is on that directory

![directory](https://github.com/germe-deb/aeiou-linux/raw/main/xkbfiles.png)

Note: the aeiou file is plain text, or C I think, but you can open that file with any editor, being vim, gnome-text-editor, micro, etc.

the original repository is https://github.com/NickG13/AEIOU
