# neo6502-bootmenu
neo6502-bootmenu is a lightweight program that reads from a configuration file to dynamically create a boot menu on the neo6502. The menu provides an easy way for users to select and run predefined programs directly from the boot sequence, streamlining access to frequently used applications.

# Configuration File Format
The boot menu entries are defined in the bootmenu.cfg file, using a CSV-style format. Each line in the file represents a menu option and follows this structure:

Display Name, installation folder, executable (*.neo, *.bas), text color code
## Example:

```plaintext
Game 1, /games, game1.bas,3
Text Editor, /apps, editor.bas,5
```

You can manually edit bootmenu.cfg using any text editor or use the included bootmenu_editor.bas tool. 

## Adding Entries to the Menu
To update the menu, either edit the bootmenu.cfg file directly or use the bootmenu_editor.bas program. This tool is at the moment just a basic program that write a new configuration file to your SD-key. A better way to edit the bootmenu will be added at some point.  

# Autostart Instructions
To have the boot menu load automatically when the system starts, add the following line to the end of your autostart.bas file:
```plaintext
run"bootmenu.bas"
```
For quick access via function keys, you can also assign the menu to a key of your choice. Add this line to autostart.bas, replacing <1-9> with the desired function key number:

```plaintext
fkey <1-9>, "run "+chr$(34)+"/bootmenu.bas"+chr$(34)+chr$(13)
```
This allows the boot menu to be launched instantly by pressing the assigned function key.
