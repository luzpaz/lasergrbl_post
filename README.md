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

--laser-on Overrides the defalt "M3" command for laser on.

--laser-no-s Suppresses the "S" word after the on command.

--laser-off Overrides the default "M5" command for laser off.

Use ";" for newlines.
<pre>
Examples:
  My laser max power setting is 1000 so if spindle speed is set
  at 900 that gives me 90%.
  
  --laser-on="M4" would produce:
       M4 S900
       
  --laser-no-s --laser-on="Turn on;100%" would produce:
       Turn on
       100%
</pre>  

**Installation :**
  
Copy **lasergrbl_post.py** to your macro directory, then select the lasergrbl post processor in your Path job.

Be sure to add --laser to the command line arguments for laser output.
