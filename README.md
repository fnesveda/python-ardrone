About:
------

This is a quick and dirty fork of <a href="https://github.com/stenix/" target="_blank">Stenix's</a> <a href="https://github.com/stenix/python-ardrone" target="_blank">python-ardrone</a> library modified to support recording the video and navdata received from and commands sent to the drone.

**Warning**: This is dirty. Very dirty. Both the code (sloppy) and the architecture (piping H.264 over stdin to a separate ffmpeg process and listening for decoded frames over stdout). But it works! And performance seems to be perfectly acceptable.

A big thank you to Stenix, Bastian Venthur and Jonathan Hunt for doing 99.99999% of the work behind this! Consider tipping Bastian Venthur's Flattr account (see the original <a href="https://github.com/venthur/python-ardrone" target="_blank">python-ardrone</a>) if you find this helpful.


Getting Started:
----------------

```python
>>> import libardrone
>>> drone = libardrone.ARDrone()
>>> # You might need to call drone.reset() before taking off if the drone is in
>>> # emergency mode
>>> drone.takeoff()
>>> drone.land()
>>> drone.halt()
```

The drone's property `image` contains always the latest image from the camera.
The drone's property `navdata` contains always the latest navdata.


Demo:
-----

There is also a demo application included which shows the video from the drone
and lets you remote-control the drone with the keyboard:

    RETURN      - takeoff
    SPACE       - land
    BACKSPACE   - reset (from emergency)
    a/d         - left/right
    w/s         - forward/back
    1,2,...,0   - speed
    UP/DOWN     - altitude
    LEFT/RIGHT  - turn left/right

To record the video, navdata and commands from the flight, start the demo as `demo.py recordingFolderPath`.

Here is a [video] of the library in action:

  [video]: http://youtu.be/2HEV37GbUow


Requirements:
-------------

This software was tested with the following setup:

  * Python 2.6.6
  * Pygame 1.8.1 (only for the demo)
  * ffmpeg in $PATH
  * Unmodified AR.Drone firmware 1.5.1


License:
--------

This software is published under the terms of the MIT License:

  http://www.opensource.org/licenses/mit-license.php

