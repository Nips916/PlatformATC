# PlatformATC

Macros and setup info for the Platform CNC ATC upgrade

This ATC macro is setup for a machine that uses the front-left corner home.  Your machine must have endstops and be able to home reliably.  I decided that the best location for the tool forks would be in the front right.  It does cause some issues with space as now you have tool holders in your face while you are trying to put work pieces down.  I didnt want to put them on the side of the Y axis because the space is more precious to me, but this could be modified to support that.  Since we have to use a compressor maybe a pnumatic actuator could be used to move the tool holder into and out of place like the ATC's on some mills.  that would free up all the space.  Right now my tool pockets are at 2 inch on center.  thats not going to work with my dust collector so I will have to adjust that.  For now, I have about 1mm on each side of the ISO20 holders, and thats not a lot of room to not fuck up.  

The spindle I'll be using for this is the JGL80 2.2kw spindle.  It will be hooked up to a HY VFD.  Its already setup and running in mach4.  This assumes the same.

I did find a setting in the Mach setup that had to do with the ATC, i'll post a picture of the setting you need to change, otherwise you will go nuts trying to figure out why the tool number is never correct.

My machines tool pockets will start at machine X29 and count from right to left.

Tool tables should be created for the tools in mach4 with correct offsets.  I may add a probing routine to auto update the offsets.  I believe your Z is adjust automatically after the tool change using your tool table heights offsets.  Ill verify that later.





Notes for me:

Tool offsets are odd.  Tool 1 is your master tool - its offset should be 0.000 in your tool offsets table.
Every other tool offset is measured by the offset to this master tool.  Use the offsets tab to set tool height with a probe (or shim) for each subsequent tool.

Break tool one?  Redo all the offsets.  Break any other, just re-touchoff that tool to reset the offset.  I will make a macro for setting all tools one by one for simplicity, but that will come later.

Also, make sure you have "Toggle Height offsets" in the offsets tab set to ON.  Tool changes should be M6 T1 + G43 H1 for setting the offset.
