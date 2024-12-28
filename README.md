# creeboard
A y dialect cree syllabic keyboard for linux, made using [kalamine](https://github.com/OneDeadKey/kalamine) ❤️

# Note

It would be extremely wise to go read up on the official [kalamine github page](https://github.com/OneDeadKey/kalamine) so you dont mess anything up. It goes into way more detail about how to make & install custom keyboard layouts. I am not responsable if you break something.

# Layout

You should be able to modify the layout in the creeboard.toml file using whatever text editor you want
Make sure to follow the [kalamine](https://github.com/OneDeadKey/kalamine) readme if modifying it. 

This layout be a simple way to help memorize syllabics.

The default layout will look similar to the example below (with shift modifier keys on top).

###### width of syllabics ruins the look of the keys but bare with me please.

```
       Vowels  P     T     K     C     M     N     S     A
┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┲━━━━━━━━━━┓
│ ~   │ ᐋ   │ ᐹ   │ ᑖ   │ ᑳ   │ ᒑ   │ ᒫ   │ ᓈ  │ ᓵ   │ ᔮ   │     │     │     ┃          ┃ Vowel A
│ `   │ ᐊ   │ ᐸ   │ ᑕ   │ ᑲ   │ ᒐ   │ ᒪ   │ ᓇ  │ ᓴ   │ ᔭ   │     │     │     ┃ ⌫        ┃
┢━━━━━┷━━┱──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┺━━┳━━━━━━━┫
┃        ┃ ᐧ    │ ᑊ    │ ᐟ   │ ᐠ   │ ᐨ    │ ᒼ   │ ᐣ   │ ᐢ   │ ᕀ   │ ᐦ   │     │     ┃        ┃ Vowel  E (with finishers in the shift modifier)
┃ ↹      ┃ ᐁ   │ ᐯ   │ ᑌ   │ ᑫ   │ ᒉ   │ ᒣ   │ ᓀ  │ ᓭ   │ ᔦ   │ ᐦ   │     │     ┃       ┃
┣━━━━━━━━┻┱────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┺┓  ⏎   ┃
┃         ┃ ᐄ   │ ᐲ   │ ᑏ  │ ᑮ   │ ᒌ   │ ᒦ   │ ᓃ   │ ᓰ   │ ᔩ   │ :   │ "   │ |   ┃      ┃ Vowel I
┃ ⇬       ┃ ᐃ   │ ᐱ   │ ᑎ  │ ᑭ   │ ᒋ   │ ᒥ   │ ᓂ   │ ᓯ   │ ᔨ   │ ;   │ '   │ \   ┃      ┃
┣━━━━━━┳━━┹──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┲━━┷━━━━━┻━━━━━━┫
┃      ┃ |   │ ᐆ   │ ᐴ   │ ᑑ  │ ᑰ   │ ᒎ   │ ᒨ   │ ᓅ   │ ᓲ   │ ᔫ   │ ?   ┃               ┃ Vowel O
┃ ⇧    ┃ \   │ ᐅ   │ ᐳ   │ ᑐ  │ ᑯ   │ ᒍ   │ ᒧ   │ ᓄ   │ ᓱ   │ ᔪ   │ /   ┃ ⇧             ┃
┣━━━━━━┻┳━━━━┷━━┳━━┷━━━━┱┴─────┴─────┴─────┴─────┴─────┴─┲━━━┷━━━┳━┷━━━━━╋━━━━━━━┳━━━━━━━┫
┃       ┃       ┃       ┃                                ┃       ┃       ┃       ┃       ┃
┃ Ctrl  ┃ super ┃ Alt   ┃ ␣                              ┃ AltGr ┃ super ┃ menu  ┃ Ctrl  ┃
┗━━━━━━━┻━━━━━━━┻━━━━━━━┹────────────────────────────────┺━━━━━━━┻━━━━━━━┻━━━━━━━┻━━━━━━━┛
```

# Installation

### windows

For building yourself, use the command
`kalamine build layout.toml --out layout.ahk` (if using autohotkey)
`kalamine build layout.toml --out layout.klc` (for root)

If installing from .klc either build it using the `wkalamine build creeboard.toml` command or using [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=102134). 
Then you should be able to install it using the windows executable files it produces :)

For autohotkey, you will need to use [autohotkey 1.1](https://www.autohotkey.com/download/1.1/)
You can also use ahk2exe to make it an executable file if you wish.

### xkb

For building yourself, use the command

`kalamine build layout.toml --out layout.xkb_symbols` (for root)
`kalamine build layout.toml --out layout.xkb_keymap` (for user)

For root you can use the command `sudo cp creeboard.xkb_symbols ${XKB_CONFIG_ROOT:-/usr/share/X11/xkb}/symbols/custom` to move it to your xkb custom folder.
For user, use the command `xkbcomp -w10 creeboard.xkb_keymap $DISPLAY` (wont display in keyboard settings)
You should now be able to add your keyboard layout (under custom) in your keyboard settings or use the command `setxkbmap custom` to set it to your keyboard.

(use `setxkbmap us` if you need to reset your keyboard layout) 

### TODO: ADD OTHER INSTALL GUIDES
