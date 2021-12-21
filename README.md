## lasergrbl_post - FreeCAD Path post processor for Grbl

This is the stock `grbl_post.py` postprocessor with a `--laser` command
line argument added, so it works normally unless you tell it to output laser
gcode.

### Usage
If `--laser` is added to the command line arguments:
- Z axis moves are removed
- K parameters are removed
- M5 is added before all rapid moves
- M3 S##### is added before each group of motion controlled moves.

**`--laser-on`** Overrides the default "M3" command for laser on.  
**`--laser-no-s`** Suppresses the "S" word after the on command.  
**`--laser-off`** Overrides the default "M5" command for laser off.  

**Important note:** use `;` for newlines.

### Examples
My laser max power setting is 1000 so if spindle speed is set at 900 that gives me 90%.

**`--laser-on="M4"`** would produce:
  **M4 S900**

**`--laser-no-s --laser-on="Turn on;100%"`** would produce:
  **Turn on**
  **100%**

## Installation

* Copy **lasergrbl_post.py** to your macro directory
* Select the lasergrbl post processor in your [Path job](https://wiki.freecad.org/Path_Job).
* Be sure to add `--laser` to the command line arguments for laser output.
