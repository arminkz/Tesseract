Tesseract 3D Printer
----

This is the git repository for my Custom made 3D Printer based on Tech2C's [Hypercube](https://www.thingiverse.com/thing:1752766) design. Some Improvments has been made to the original design.


### Features

* Bowden extrusion
* CoreXY kinematics
* BLTouch automatic bed leveling
* Semi-Industrial standard
* Open source and fully customizable

### Firmware

Firmware is based on [Klipper](https://www.klipper3d.org/) (previously Marlin). Klipper splits the work between a host and the board: all the motion planning runs on a Raspberry Pi, while the Arduino Mega + RAMPS 1.4 board only executes the resulting step timings. The Pi runs [Mainsail](https://docs.mainsail.xyz/) as the web interface, with [Moonraker](https://moonraker.readthedocs.io/) as the API layer behind it.


### Configuration

All host configuration lives under [klipper/config/](klipper/config/):

| File | Purpose |
| --- | --- |
| [printer.cfg](klipper/config/printer.cfg) | Kinematics, steppers, heaters, BLTouch, LCD and macros |
| [moonraker.conf](klipper/config/moonraker.conf) | API server, update manager, print history |
| [mainsail.cfg](klipper/config/mainsail.cfg) | Macros required by the Mainsail interface |
| [crowsnest.conf](klipper/config/crowsnest.conf) | Webcam streaming (1280x720 MJPEG on port 8080) |
| [timelapse.cfg](klipper/config/timelapse.cfg) | Timelapse recording macros |
| [sonar.conf](klipper/config/sonar.conf) | Keeps the WiFi connection from going to sleep |

Copy these into `~/printer_data/config/` on the host and restart the Klipper and Moonraker services.
