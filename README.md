TLDR
1. Download SharpKeys and swap the CMD (`⌘`) key with the CTRL (`^`) key. Make sure it is vice versa as well.
2. Download AutoHotKey
3. Run scripts/english/mac.ahk

Onekeyboard - Apple Keyboard Layout under Windows
=================================================
This small autohotkey script simulates the Macintosh OSX keyboard layout under Windows.
## About this project
This project is for everyone who wants to use the Mac OSX keyboard layout under Windows too. 
I started this project because my work forced me to regularly switch between OS X and Windows. This was really frustrating for me, because even the basic keyboard shortcuts were different and I had to adapt for the changes every time again. 

As I'm quite happy with the Mac keyboard layout I decided to simulate this layout under Windows. For instance, I wanted to press `⌘ + c` instead of `^ + c`. 

As I couldn't find very useful other layouts on the Internet and the support of VMs such as Parallels Desktop were quite unsatisfying, I decided to start fresh and create my own layout.

## What exactly does it do?
It simulates the following Mac OSX keyboard behavior under Windows:

 * Text navigation (`⌥ + Left`, `⌘ + Shift + Left`, ...)
 * Copy&Paste (`⌘ + C`, `⌘ + X`, `⌘ + V`)
 * Symbols (`@`, `[](){}/|`, ...)
 * Some typical OSX shortcuts (`⌘ + Q`, `⌘ + ⌥ + ESC`, `⌘ + ⇧ + Z`, ...)
 * Finder shortcuts for Explorer (`⌘ + DOWN`, `⌘ + Ö`, `⌘ + I`, ...)
 * Windows key is still accessible through CTRL (`^`)

## How to get it working
### Requirements
 * [autohotkey][autohotkey] - lightweight program to interpret customized hotkeys.
 * [mac.ahk][ahk] script to correctly map the hotkeys (e.g. the script that does all the work).
 * Some customization to swap the CMD (`⌘`) and the CTRL (`^`) keys lowlevel (see the following paragraph).
 * German keyboard layout (or you probably need to adjust the [mac.ahk][ahk] script for your language).


### Installation Guide
At first we have to swap the CMD (`⌘`) key with the CTRL (`^`) key. This is something that we shouldn't do with autohotkey, because it is more reliable to change such an important key on a lower level. There are multiple options to achieve this:

 * If you are using Windows through a VM such as Parallels Desktop, you could swap the keys by using the Parallels shortcut settings ([Example](images/parallels.png)).
 * You could swap the keys by mapping them through the registry by applying the [ctrlswap.reg][reg] file.
 * You could also use a free program to swap the keys (such as [KeyTweak][keytweak]) but it produces the same registry entry anyway. You could use the [ctrlswap.ktw][ktw] configuration file for [KeyTweak][keytweak] to swap the keys.


After you have successfully swapped the two keys, you just need to install autohotkey and start the [mac.ahk][ahk] script.
If you don't use a German keyboard layout, you probably want to adjust the [mac.ahk][ahk] script to map special characters (such as `[](){}?@<>`) to the correct position. You are welcome to do so and create a pull request :)

### Todo aka What's next?
 * Splitting the ahk script in multiple scripts to
 * support other layouts (English, Spanish, ...)
 * Shortcuts for other applications


[ahk]: https://github.com/andi-w00t/onekeyboard/blob/master/scripts/german/mac.ahk
[reg]: https://github.com/andi-w00t/onekeyboard/blob/master/registry-ctrlswap/ctrlswap.reg
[ktw]: https://github.com/andi-w00t/onekeyboard/blob/master/keytweak-ctrlswap/ctrlswap.ktw
[autohotkey]: http://www.autohotkey.com
[keytweak]: http://www.tucows.com/preview/327616/KeyTweak
