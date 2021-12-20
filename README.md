<h1 align="center">lasergrbl_post</h1>

## FreeCAD Path post processor for Grbl.

This is the stock grbl_post.py postprocessor with a --laser command
line argument added, so it works normally unless you tell it to output laser
gcode.

If --laser is added to the command line arguments:
- Z axis moves are removed
- K parameters are removed
- M5 is added before all rapid moves
- M3 S##### is added before each group of motion controlled moves.

Install of lasergrbl_post.py for using in the FreeCAD Path module:  

- Personal install :
  
Copy **lasergrbl_post.py** to your user macro directory, then select the lasergrbl post processor in your Path job.

Be sure to add --laser to the command line arguments for laser output.
