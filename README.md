# neo6502-bootmenu
neo6502-bootmenu is a lightweight program that reads from a configuration file to dynamically create a boot menu on the neo6502. The menu provides an easy way for users to select and run predefined programs directly from the boot sequence, streamlining access to frequently used applications.

# Configuration File Format
The boot menu entries are defined in the bootmenu.cfg file, using a CSV-style format. Each line in the file represents a menu option and follows this structure:

Display Name, installation folder, executable (*.neo, *.bas)
Example:

Game 1, /games, game1.bas,
Text Editor, /apps, editor.bas,

You can manually edit bootmenu.cfg using any text editor or use the included create_bootmenu.bas tool for easier updates.

# Adding Entries to the Menu
To update the menu, either edit the bootmenu.cfg file directly or use the create_bootmenu.bas program. This tool allows you to modify the menu entries on the neo6502 itself. After editing, run the program to generate a new bootmenu.cfg file, which will be saved to your USB key.

# Autostart Instructions
To have the boot menu load automatically when the system starts, add the following line to the end of your autostart.bas file:

run"bootmenu.bas"
For quick access via function keys, you can also assign the menu to a key of your choice. Add this line to autostart.bas, replacing <1-9> with the desired function key number:

fkey <1-9>, "run "+chr$(34)+"/bootmenu.bas"+chr$(34)+chr$(13)

This allows the boot menu to be launched instantly by pressing the assigned function key during startup.
