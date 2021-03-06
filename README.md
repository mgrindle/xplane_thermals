xplane_thermals
===============

Author: Alex Ferrer
License: GPL 2014


X-Plane plugin to generate more realistic thermals 

The current X-Plane (Ver 10.30+) thermal model is quite simplistic. This is an attempt to create a plugin that simulates more realistic thermals.

Basic concept:
Create a fixed or random list of thermals with lat,lon,thermal diameter, thermal strength.
While flying, detect collision between the aircraft and the thermals, apply the lift to the aircraft.


Advanced concepts already implemented:

- Regular Thermals (not dynamic lift) tend to have a strong core of lift followed by outward softer layers of lift.

- Thermals drift with the wind as they gain altitude. 

- Thermals rise till they reach cloudbase or the top of the lift. At this point they dwindle off. 

- When a wing of a plane hits a thermal and the other wing does not, the plane tends to roll against the lift.

- When the wing of the plane is on a roll, the thermal roll factor is reduced (less arm momentum) 

- Thermals gain and loose strength along with the height of the sun in the sky (accounting for seasons)


A random thermal generator menu allows the user to select quantity of thermals, size and strength. The thermal placement is random, but smart enough not to set thermals above water surfaces. 

A thermal visualization aid (shows markers where the thermals are) exists with an option to turn it on/off on the plugin menu.

UPDATE
-----
- Loading CSV hotspots from https://thermal.kk7.ch/ added. Download your fav. thermal hotspots and put the hotspot.csv into your X-plane root directory


TODOs
-----

- Thermals have cycles, begin, middle, end and they tend to keep a basic timming.

The idea is to simulate the begin, middle and end stages of a thermal that go on cycles throughout the day. 
Begin: after the sun heats the ground and a big parcel of humid air gets warm enough a giant "bubble" of hot air raises into the air (because hot air is lighter than the surrounding air) at this point the thermal is usually small in diameter and starts getting stronger. 

Middle: the "bubble" of hot air is already climbing, it gets wider and has the strongest lift

End: once the whole bubble has reached cloudbase, the air inside and outside the bubble are equal, so it stops moving up. but still has remaining lift until it eventually dies. 

The lengths of this cycles varies depending on temperature, humidity, altitude etc. Glider pilots learn to recognize this patterns and use them to know when to leave a thermal. 

- Thermal streets
- Clouds at the top of the thermal (* this is a big one, but I don't know how to do it yet) 


Installation
------------

This is a Python plugin, so the python interface is required. ( http://www.xpluginsdk.org/python_interface.htm ) For installation copy the Python files to the X-Plane Resources/PythonScripts folder so that the Python plugin can find them.

As a helper, I am using Easy Dataref access class from Joan Perez i Cauhe, and I am including the class on the sources. 
Other than that, all is needed is PI_ThermalSym, thermal_model.py and world.py anything else is test stuff or helpers. 

V 0.3 has a nice menu to define thermal parameters, better thermal simulation, better performance and reduced memory space. 


Older versions
--------------

V 0.2 (current) Is already quite usable. It has a matrix of 10000x10000 ~70nm^2 , implements all the concepts listed above. At this point there are several variables (wind, thermal tops, thermal generation) that are hardcoded and require changes of code if you wish to modify.

V 0.1 it works based on a 10x10 matrix that repeats itself. it works, but is just a sucky proof of concept.


About the author
----------------

I have about 20 years experience flying thermals on Gliders, Paragliders and Ultralight aircrafts. I've owned and flown (sp?) many diferent gliders from a very slow 1-26 to ASK-21.  I've flown extensively on the Texas plains and on the mountains of Peru, so I feel I've got a good idea of how a thermal should feel when you fly a glider on X-Plane. I hope that this plugin helps improve the glider flying experience on X-plane for all. 
