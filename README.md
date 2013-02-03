dc.files.kbd
------------

This is my Keyboard Layout, which I've spent a considerable amount of time refining.
This project is part of my dotfiles, which can be found at http://github.com/dcunited001/dc.files.
This project also includes my keybindings for zsh, vim, emacs and pretty much any other program.
I put them all in one repo so they could be easily shared as a complete profile.

> On OSX: you will need to install KeyRemap4MacBook, PCKeyboardHack, and NoEjectDelay.
> They are all free and have awesome default settings, regardless of whether you add my private.xml settings.

![ScreenShot](https://raw.github.com/dcunited001/dc.files.kbd/master/dc-keyboard.jpg)

Hyper Key
=========

I've remapped Function to Hyper.  It is actually set to 'All Modifiers', but this
is about as close as you can get, as far as I know.  It can still be interpreted in
Emacs as Hyper.

Uber Key
========

For the 'Uber' Key to work, you will need to check my PCKeyboardHack Settings:

- Caps => Escape
- CMD-R => CMD-L
- Escape => CMD_R

Right now I'm using the Uber Key as an OS-Level shortcut key, which doesn't conflict in any way with Super(Command).  Combined with QuickSilver, I have it set in OSX to switch between Apps and Spaces:

- Uber+! => iTerm
- Uber+@ => gMail (FluidApp)
- Uber+# => Twitter
- Uber+C => Chrome
- Uber+P => Google Voice (FluidApp)
- Uber+Left => Space Left
- Uber+Right => Space Right

This can save you tons of time.  But more importantly, it saves you tons of short-term memory, versus Alt-Tabbing.  It's about changing your workflow to better suit your brain.

Alt-Tabbing is great when you have 2 programs open.  Any more than that and you have to be able to recall how deep in the 'tab-stack' that one app is.  You can waste up to 10 seconds every time.

Not to mention, when you Alt-Tab, you are forced to resort to visual recognition to find that app, which needlessly wastes your brain's CPU cycles.  When you have a hotkey set, you actually begin to use muscle memory instead.

To Install
==========

- Install KeyRemap4MacBook, PCKeyboardHack, and NoEjectDelay.
- Restart your computer multiple times!
- Copy the contents of the KeyRemap4MacBook folder to "~/Library/Application Support/KeyRemap4MacBook"
- Now that my custom settings are available in KeyRemap4MacBook, choose the ones you like and enable them.

> Note: some settings may clash with others.  If you run into problems, give me a shout.  And this is a work in progress, so it's not polished.

TODO
======

- Switch to a DVORAK layout.  Hopefully soon, but I don't want to cross my fingers...
- Figure out what to do with Shift+Digits and Shift+Consumer.
- Move the Consumer Keys (play/pause/etc) from Uber+Consumer to Shift+Consumer?
- Swap ` and ~
- Find a better location for |
- Application-Specific/Language-Specific Keys?
