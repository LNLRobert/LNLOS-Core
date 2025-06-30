# Welcome
Welcome to LNLOS! 
(This is to be paired alongside: https://github.com/LNLRobert/LNLOS-ConfigFiles)

If youre reading this on a unit, your config files should already be included, but you will still need to complete your printer setup.

Open your printer.cfg file, and uncomment (remove the "#") symbol before each of the relevant components for your machine.

Find the following sections and uncomment the appropriate line -> Board Assignment, Machine Assignment, and Sensors 

Printer 1 will use the upper rear usb port on the pad, and printer 2 will use the lower rear usb port.

Completed Sections will look like the following:

############################################################
### BOARD ASSIGNMENT ### 8 bit units have a bigger sd card slot / usb a cable, 32 bit units connect with a usb-c cable and have a microsd card slot
############################################################
# -- 8bit units -- #
#[include LNL3dOS/boards/Mega2560.cfg]
# -- 32bit units -- #
[include LNL3dOS/boards/HC32F460.cfg]
# -- 32bit large units with high speed y stepper driver -- #
#[include LNL3dOS/boards/HC32F460-HSYStepper.cfg]

############################################################

############################################################
### MACHINE ASSIGNMENT ### pick one
############################################################
#[include LNL3dOS/printers/TL-H2.cfg]
[include LNL3dOS/printers/TL-D3.cfg]
#[include LNL3dOS/printers/TL-D5.cfg]
#[include LNL3dOS/printers/TL-D6.cfg]
############################################################

############################################################
### SENSORS ### enable the relevant sensors you are actively using
############################################################
#[include LNL3dOS/sensors/adxl.cfg]
#[include LNL3dOS/sensors/BLTouch8Bit.cfg]
#[include LNL3dOS/sensors/BLTouch32Bit.cfg]
# use safe home if running probe to z optical sensor
#[include LNL3dOS/sensors/safehome.cfg]
#[include LNL3dOS/sensors/lis2dw.cfg]
# you may use one of the two below, but not both at the same time
[include LNL3dOS/sensors/EuclidProbe.cfg]
#[include LNL3dOS/sensors/FilamentRunoutSensors.cfg]
############################################################

If you would like to change your hotend type, extruder type, or other settings, you may do so in printer.cfg.
You can also change your nozzle size here if necessary

Once you have uncommented your necessary sections, click save and restart at the top of the screen. 

Once your machine reboots, if printer.cfg was completed successfully, you will be greeted with a dashboard showing printer info. 

Using the provided Pad, navigate to Configuration -> Z Calibrate. Select Start -> Endstop Calibration. Your print head will move over to the center of the bed. Using the menu, lower nozzle and perform a paper level test until snug without too much friction. Click accept and save when prompted. If you have a probe, repeat this process, first equipping your probe and selecting Probe on the second round. Toolhead will probe a point on the bed and raise. Remove the probe and lower toolhead like you did for endstop calibration. Click apply and save when prompted. 

From here, tram your bed with Configuration -> Bed Level. If you have a probe, use Screws Adjust and turn the screws according to the output results. Repeat this process until all screws read less than 6 degrees of turning. The values indicate to turn the bed screw that many minutes as if it were a clock, with CW indicating Clockwise, CCW indicating CounterClockwise. If you do not have a probe, use this same menu but tap each of the corner icons and manually adjust each corner with a paper test.

If you have a probe, I also then recommend you run a bed mesh, using Configuration -> Bed Mesh -> Calibrate. Save this mesh. If you start having first layer problems that cant be solved with fine tuning your z offset, re-run screws tilt and bed mesh. 

Once these have been completed, you should be good to go and upload your first gcode to the gcodes menu in Mainsail and start printing.

Happy Printing! 