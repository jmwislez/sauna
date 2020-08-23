# Building an outside sauna from scratch

<img src="https://raw.githubusercontent.com/jmwislez/sauna/master/pictures/IMG_0201%20-%20skeleton%20installed.JPG" width="300px"> <img src="https://raw.githubusercontent.com/jmwislez/sauna/master/pictures/IMG_0248%20-%20covered%20with%20moist%20protection.JPG" width="300px"> <img src="https://raw.githubusercontent.com/jmwislez/sauna/master/pictures/DSC_2306%20-%20sauna%20finished.JPG" width="300px">

<img src="https://raw.githubusercontent.com/jmwislez/sauna/master/pictures/IMG_0210%20-%20installing%20isolation%20(internal%20view).JPG" width="300px"> <img src="https://raw.githubusercontent.com/jmwislez/sauna/master/pictures/IMG_0244%20-%20benches%20installed.JPG" width="300px"> <img src="https://raw.githubusercontent.com/jmwislez/sauna/master/pictures/2020-05-10%2015.40.44%20-%20shower.jpg" width="300px">

## What this repository provides

In this repository, you'll find 3D designs (FreeCAD) for an external sauna I built, as well as for a shower.  It also provides materials and costs (2013 in Belgium), as well as snapshots of the design and pictures during building.  Through cost-effective procurement, I was able to limit the material costs to about 2000 euro, excluding electric installation.

## The layout and dimensions

The sauna was to be installed outside, under an existing 2.2m high 3x3m hood of a garden shed.  Hence, there is no roof as part of the sauna design. A stabilized platform was already available.  

<img src="https://raw.githubusercontent.com/jmwislez/sauna/master/snapshots/sauna%20v3%20-%20available%20volume.png" width="800px">

The available volume under the hood was the main driving factor for the dimensions.  Within these limitations, I searched for an optimal layout with minimal inner dimensions (to reduce the volume and hence heating costs), and considering anthropometric dimensional data (95th percentile).  The sizes were then fine-tuned to the available wood sizes.  I am quite satisfied with the selected layout, as the sauna is comfortable and makes good use of the available space.

<img src="https://raw.githubusercontent.com/jmwislez/sauna/master/snapshots/sauna%20v3%20-%20internals.png" width="800px">

For the height, this meant one bench at 42cm height above the sauna floor (typical ergonomic sitting height), one at 84cm (to sit with feet on the lower bench), and then a sitting height of at least 100cm (95th percentile) between the top bench and the roof - I ended up at 104cm.  Given the limitation in the vertical space, I had to limit the floor and ceiling isolation thickness to 10cm only.  Total external height is 213cm, total internal height is 188cm.

For the internal width, I took 2m lying length (95th percentile), and for the depth 1.8m (50th percentile, and fine for me).  What I forgot is to consider that two persons lying down will collide in the corner.  Hence, if you have room, take some extra margin.

As for the walls, they have a total thickness of 21cm.

## Construction

The construction is based on a wood skeleton, which was assembled wall by wall in a workshop.  

These are the layers for the walls (from inside to outside), totalling 21cm:
* Internal wood finishing, composed of 95mm x 14mm tongue-and-groove planks [NL: saunaschroten] (second choice nordic spruce, dried for use in sauna), attached with mounting clips [NL: profielhoutklemmen].
* Reflective vapourshield (integrated with the glasswool), finished with aluminium tape.
* 60cm wide 15cm thick glasswool (Isover) with integrated reflective vapourshield, carried by the wood skeleton.
* Thin MDF plates for covering the glasswool.
* Vapour permeable breathable membrane [NL: dampscherm] (Pro Clima SOLITEX WA).
* Air layer (slating battens as spacers [NL: panlatten]).
* External wood finishing, composed of 170mm x 19mm tongue-and-groove planks [NL: schroten], treated for outdoor use with Xyladecor.

For reasons of accessibility, the top and bottom structures were fully outfitted with reflective layer, glasswool and vapour shield before installation, while the side walls were outfitted once installed.

## Benches 

The benches are based on solid beams anchored to the main skeleton structure using big screws.  The benches are made of Abachi-wood.  This is an excellent choice, but be careful when working that wood: it generates a very fine dust which gives headaches that last for days.  Work outside, or with a mask.

<img src="https://raw.githubusercontent.com/jmwislez/sauna/master/pictures/IMG_0233%20-%20frames%20for%20benches.JPG" width="450px"> <img src="https://raw.githubusercontent.com/jmwislez/sauna/master/pictures/IMG_0244%20-%20benches%20installed.JPG" width="300px">

## The heating system

For 100 euro I bought a second hand 6 kW electric heater, a controller with sensor, a light, two headrests, a wooden bucket and a wooden spoon.

For a 6 kW heater (any heater above 4.5 kW), a three phase electricity installation is needed.  Check what is needed to do this legally and safely at your place.  I installed an underground EXVB 5G2.5mm2 cable in a red plastic tube at a depth of 60cm, which led to a separate fuse board with a 30mA differential fuse (sauna is a wet zone) and a 3-phase 16A overcurrent fuse.  The cables that led power into the sauna (for the heater and the light) was a SIHF cable given the heat endured in a sauna.

Be sure to include ventilation. Foresee a wide slit underneath the heater for air input, and an exit halfway the opposite wall.

## The shower

Given the absence of a sewer connection, the water needs to infiltrate into the ground.  Also, I wanted to be able to easily empty or lower the levels in the water pipes in and above the ground in case of frost.  Finally, I wanted to have the possibility for having sun-heated water.  All this ended up in a way too complex set of pipes and valves (which I can draw and post if there is interest), but it works!

## Using the sauna

The sauna is comfortable for 2-3 people lying down, and up to 6-7 people sitting.  

Heating at 6 kW takes about 45-60 minutes, after which the heater duty cycle is around 50%.

## Goodies

I installed old speakers at the bottom rear corners (coolest places), and outside I installed a watertight box with a car amplifier inside.  This way, I can connect an audio source with a 3.5mm stereo plug, and play music inside.

In an attempt to keep humidity as low as possible, I added an ESP8266-based controller, comparing internal and external absolute humidity (with DTH-22 sensors), and starting fans when the outside absolute humidity is lower.  In practice, this ventilation is only active when the sauna is heated.  Nice side effect is that I have temperature and humidity logging over MQTT, which I can monitor with Home Assistant.  The system can also warn me on my phone when the sauna is hot.  In practice, the sensors fail regularly, which I need to address by using soldered connections.

I also attempted to have a "bio-sauna" effect by using a WiFi-controlled RGB LED-bulb, with colour settings controlled by the ESP8266.  This worked well in development (even have a nice mode with the bulb colour going from blue to red while the sauna is heating), but in practice the WiFi connection of the bulb is unstable when the sauna temperature is high, making a proper control impossible.

## What I would do differently

* If room is available, increase the isolation thickness everywhere to 20cm.
* I would make the sauna slightly wider, to avoid leggs colliding when 2 people are lying down on the top benches.
* The side top bench is now 60cm wide, but 70cm would be even more comfortable.
* The wooden door is nice, but throughout seasons it needs retuning to close well and open easily.
* After I applied the outer wood layer (one year later), I found out the door would not open further than 90 degrees any more.



