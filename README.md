# PlatformATC

Macros and setup info for the Platform CNC ATC upgrade

This ATC macro is setup for a machine that uses the front-left corner home.  Your machine must have endstops and be able to home reliably.  I decided that the best location for the tool forks would be in the front right.  It does cause some issues with space as now you have tool holders in your face while you are trying to put work pieces down.  I didnt want to put them on the side of the Y axis because the space is more precious to me, but this could be modified to support that.  Since we have to use a compressor maybe a pnumatic actuator could be used to move the tool holder into and out of place like the ATC's on some mills.  that would free up all the space.  Right now my tool pockets are at 2 inch on center.  thats not going to work with my dust collector so I will have to adjust that.  For now, I have about 1mm on each side of the ISO20 holders, and thats not a lot of room to not fuck up.  

The spindle I'll be using for this is the JGL80 2.2kw spindle.  It will be hooked up to a HY VFD.  Its already setup and running in mach4.  This assumes the same.

I did find a setting in the Mach setup that had to do with the ATC, i'll post a picture of the setting you need to change, otherwise you will go nuts trying to figure out why the tool number is never correct.

My machines tool pockets will start at machine X29 and count from right to left.
