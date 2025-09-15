# Core R-Theta Menu System

![Menu While Printing](https://user-images.githubusercontent.com/61329420/76150822-5ff00c80-607c-11ea-942c-f297da326593.jpg)

[Here's a video giving a tour of the menu.](https://youtu.be/9U0oqMW-FwY) Courtesy of @jadonmmiller.

This is the menu for the [Core R-Theta 4 axis 3d printer](https://github.com/EmmanuelMess/Core-R-Theta-4-Axis-Printer-UNR-Improvements).
This menu system is an adaptation of @jadonmmiller 's Ultimate Duet Menu System which works for Duet.
It has some changes to support the extra B and C axis. 
 
## What are these files and how do I use them?
 To configure the board with this new display, just add `M918 P1 E4` to your configuration file.  
 And copy paste the files from the lastest release in the [Github Releases Page](https://github.com/EmmanuelMess/CoreRThetaMenuSystem/releases),
 to a "Menu" folder on the board's SD card. 
 That should be all that's needed for a basic setup--enjoy your new display!
 
 ## Key Features
 - Print files from the external SD card (Not supported in any other known menu system)
 - Control Speed, Extrusion, Babystepping, Fans, and Heaters all from the homepage
 - Supports running custom macros from the /macros folder on the main SD card
 - Easy manual and automatic bed leveling
 - Deploy and Retract a Z Probe using the native commands.
 - Allows control of the power supply using `M80` and `M81` commands
 - Easily Customizable
 
## Menu Structure
 The main overview screen shows the most-used settings, with an option to scroll right for more print settings. 
 (speed, extrusion, and baby-stepping) The menu offers options to move axis, disable motors, control the printer,
 run macros, and many other features!
 
## What you might want to change
 While these menu files are a good starting point, some things will need changed. Namely, the fan and
 heater numbers, as well as a few gcode scripts for things such as loading and unloading filament.
 Here's a list:
 
 - File main - Heater and fan numbers may need to be changed. By default, the bed is heater 0, the extruder 
 is heater 1, and the print cooling fan is fan 0.
 - File preheat - Heater numbers may need to be changed here as well. You can also change the preset
 temperatures. The instructions are in the file.
 - File moveExtruder - Once again, the temperature display will need to be changed to fit your heater
 configuration.
 - File changeFilament - This page shows the hotend temperature as well, and will therefore need updated.
 - Script unload.g - Found in the /scripts folder, this gcode file unloads the filament from your printer.
 by default it's set up for a direct-driven E3D V6 hotend with a Bondtech BMG extruder.
 - Script load.g - The same story as the unload file, but to load filament. :)
 - Script autoLevel.g - The menu runs this script to auto-level the bed. Currently it homes all the axis,
 then calls G32.
 - Scripts goToLevelPoint1.g, etc. - These scripts are used in the manual leveling procedure and should
 move the head over one leveling point (likely a leveling screw) per file.
 
## Features waiting on firmware compatability
 These are features I'd like to add to the display system but aren't yet available in the firmware:
 
 - Only show SD cards when they're mounted (Supported for the internal card, but not the external yet.)
 - Show print estimations based on the slicer
 
## Inspiration
 This repository is based on the Ultimate Duet Menu System by @jadonmmiller.

 I owe a big thank you to Github user @tinkerlifeprojects. I really liked his menu system and used the
 basic framework to write mine. I also want to thank @mudcruzr, as I used some ideas from his menus as
 well.
 
 I had trouble finding menu systems contributed by other users, so here's a list of some of the other
 currently available files:
 
 [Tinkerlifeproject's TinkerLCD](https://github.com/tinkerlifeprojects/DUET3D_12864LCD_MenuFiles)
 
 [Mudcruzr's LCD files](https://github.com/mudcruzr/Duet-Maestro-12864-Menu-Files)
 
 [Sidic101's improvements on Mudcruzr's menu](https://github.com/Sidic101/Duet-Maestro-12864-Menu-Files)

## Contributing
 I tried to make these files the best out there, but they're by no means perfect! Please feel free to suggest
 any changes or features that you think would be helpful. Thanks!
