# Mac-OS-X-German-PC-Keyboard-Layout
The missing German PC Keyboard Layout for OS X

## Install
Simply copy "german-pc.keylayout" to "/Library/Keyboard Layouts"

## Issues
There are two known issues that can not be fixed just by the keyboard layout.
1. The "Menu" or "Application" key is not recognized as right-command.
This can be fixed with the software "Karabiner-Elements" by adding a
"simple modification" from "application" to "right_command".
2. Another issue is that some keys do not behave as expected in the macOS
environment. Again "Karabiner-Elements" can help.
I recommend the following complex modifications:
* "PC-Style Shortcuts" -> "PC-Style Home/End"
* "Finder" -> "Use Return as Open and Use Fn+Return as Rename"




# Arabic phonetic layout for german keyboards for X11

## Install
cp X11/ara_phonetic_ger /usr/share/X11/xkb/symbols/

Add the following to "/usr/share/X11/xkb/rules/evdev.xml" just before "</layoutList>".
<layout>
  <configItem>
    <name>ara_phonetic_ger</name>
    <!-- Keyboard indicator for Arabic layouts -->
    <shortDescription>ar</shortDescription>
    <description>Arabic (Phonetic for German keyboards)</description>
  </configItem>
</layout>

Or simply execute:
sed --in-place 's/<\/layoutList>/<layout> \
  <configItem> \
    <name>ara_phonetic_ger<\/name> \
    <!-- Keyboard indicator for Arabic layouts --> \
    <shortDescription>ar<\/shortDescription> \
    <description>Arabic (Phonetic for German keyboards)<\/description> \
  <\/configItem> \
<\/layout><\/layoutList>/' /usr/share/X11/xkb/rules/evdev.xml
    
logout and login again
