<!-- .element: data-background-image="./img/chicken-at-front-door.jpg" -->
# Automatic Chicken Door HOWTO

## No, it will not hurt the chicken

By [Adam Monsen](http://adammonsen.com), VP Engineering at [C-SATS, Inc.](https://csats.com)



## Note to self

Use PgDn to advance through slides



This is the story of four chickens


<!-- .element: data-background-image="./img/four-chx.jpg" data-background-size="contain" -->


Who meet one hungry little furball


<!-- .element: data-background-image="./img/800px-Waschbär4.jpg" data-background-size="contain" -->


And quickly become a flock of one.


This is the story of...


## _The Chicken Who Lived_


<!-- .element: data-background-image="./img/suspicious.jpg" data-background-size="contain" -->

## Meet Louise

Our stealthy Welsummer


Louise wants to live and wants a new flock.

First she needs a safer home.

One with an automatic door!



<!-- .element: data-background-image="./img/whole-coop.jpg" data-background-size="contain" -->


<!-- .element: data-background-image="./img/door-closed.jpg" data-background-size="contain" -->


<!-- .element: data-background-image="./img/door-open.jpg" data-background-size="contain" -->


<!-- .element: data-background-image="./img/installed-rpi.jpg" data-background-size="contain" -->



Louise likes the new coop but when it comes to the door she is...


<!-- .element: data-background-image="./img/suspicious.jpg" -->

# Suspicious!


She'll get over it.


Let's talk about chickens.



# Chicken primer


1. Never get wet
1. Never expose to sunlight
1. Never feed after midnight

SpeakerNote: Sorry, wrong primer (see Gremlins - 1984 movie)



# Real chicken primer


<!-- .element: data-background-image="./img/how-chicken-works.svg" data-background-size="contain" data-background-color="lightgrey" -->

SpeakerNote: They also eat bugs and rocks.


1. Food → Chicken → Egg
1. Chicken not smart
1. Must be locked in at night



# Must be locked in at night


<!-- .element: data-background-image="./img/800px-Waschbär4.jpg" data-background-size="contain" -->

SpeakerNote: Photo credit Tobias Mercer. Licensed GFDL, CC-by-2.5. Source: https://commons.wikimedia.org/wiki/File:Waschb%C3%A4r4.jpg


Chickens get in the coop before dusk.

They are pros at this.


All you need to do is lock up the coop at night


_Every night_


And open it in the morning

SpeakerNote: so they can free range and stuff


_Every morning_


_even in the summer when that sun comes up really early and the chickens really really wanna get out at the buttcrack of dawn_


Yeah no. Let's automate it!


# TL;DR 🐔

1. Plan project
1. Buy parts
1. Practice mini-projects
1. Prototype
1. Install
1. Celebrate



# Hardware


## Parts summary

1. Raspberry Pi, motor, sensors
1. Wood, string, magnets


## Parts detail

| Item           | Source      | Cost |
| -------------- | ----------- | ---- |
| Raspberry Pi   | Amazon      | $50  |
| Soldiering kit | Radio shack | $35  |
| Starter kit    | Amazon      | $30  |
| Camera         | Amazon      | $24  |
| Wires          | Amazon      | $15  |
| 12V DC motor   | Amazon      | $14  |

(continued below)


| Item           | Source      | Cost |
| -------------- | ----------- | ---- |
| Fuses & holder | Amazon      | $13  |
| 32GB SD card   | Amazon      | $13  |
| Mag sensors    | Amazon      | $7   |
| Test leads     | Amazon      | $6   |
| Power supply   | SparkFun    | $6   |

### Total: $213

SpeakerNote: Minus tax and shipping/handling. See last slide for links.



<!-- .element: data-background-image="./img/pi-in-case.jpg" data-background-size="contain" -->

SpeakerNote: Raspberry Pi w/case by Vilros: $50


<!-- .element: data-background-image="./img/rpi-3-diagram.jpg" data-background-size="contain" -->

SpeakerNote: Raspberry Pi w/case by Vilros: $50


<!-- .element: data-background-image="./img/starter-kit.jpg" data-background-size="contain" -->

SpeakerNote: Adeept starter kit: $30


<!-- .element: data-background-image="./img/fisheye-camera.jpg" data-background-size="contain" -->

SpeakerNote: Fisheye night-vision camera: $24


<!-- .element: data-background-image="./img/wires.jpg" data-background-size="contain" -->

SpeakerNote: Wires: $15


<!-- .element: data-background-image="./img/motor.jpg" data-background-size="contain" -->

SpeakerNote: Motor: $14


<!-- .element: data-background-image="./img/fuse.jpg" data-background-size="contain" -->

SpeakerNote: Fuse holder & fuses: $13


<!-- .element: data-background-image="./img/sd-card.jpg" data-background-size="contain" -->

SpeakerNote: 32GB SD card: $13


<!-- .element: data-background-image="./img/mag-sensor.jpg" data-background-size="contain" -->

SpeakerNote: Bag of mag sensors: $7


<!-- .element: data-background-image="./img/test-leads.jpg" data-background-size="contain" -->

SpeakerNote: Test leads: $6


<!-- .element: data-background-image="./img/power-supply.jpg" data-background-size="contain" -->

SpeakerNote: Regulated power supply: $6



# Software


## Door control flow

[![Door control flow diagram](./img/control-flow.svg)](./img/control-flow.svg)


## TODO: add Slack screenshot


## TODO: more about software here



# FIXME - REDO THIS SECTION


<!-- .element: data-background-video="./vid/door-open.webm" -->


<!-- .element: data-background-video="./vid/settle-in.webm" data-background-size="contain" -->



## More ideas

* [Use Raspian OS](https://www.raspberrypi.org/downloads/raspbian/)
    * codename: "stretch" (with desktop)
* Try the camera: do a time-lapse video
* Try a project from a Starter Kit (e.g. Adeept)

SpeakerNote: Add mouse + keyboard + monitor for a perfect kid desktop!


* Ask for help!
* Try combining sensors / lights / camera
* Use lots of emoji 🐔 🚦 😓 ⏰ 🏁 🐣 🌇 📡 📷 🚧



## Lessons learned

* If the Raspberry Pi won't boot, unplug all peripherals and try again. If USB ports are full, peripherals may draw too much power.
* Get help, ask around. Call friends. Pair up. Find a local maker space.
* I'm incredibly lucky to have a brilliant, patient partner who is great at woodwork and code review.

(continued)


* Use a 32GB flash card. I bricked a 64GB card.
* Easy: camera. Plug & play!
* Hard: door actuator: spindle, dealing with drag/resistance. Tight tolerance.
    * Temperature and humidity affect (wooden) door operation.
* Hard: 12V DC motor. L9110 controller is tricky to wire. Software is complex. Wasted time on [PWM](https://learn.sparkfun.com/tutorials/pulse-width-modulation).

(continued)


* Easy: magnetic (hall effect) sensor.
* Hard: Adeept Python photoresistor code didn't work, but C code did.
* Easy: posting messages to IRC or Slack.
* Early mistake: motion alerts for all chicken movement.
* [Adeept source is on GitHub](https://github.com/adeept/)
* Nocturnal predators may also hunt during the day, and there are other daytime predators too.



## Links to buy parts

* [Raspberry Pi 3 model B with clear case by Vilros](https://www.amazon.com/gp/product/B01D92SSX6/)
* Soldering iron, "helping hands", rosin-core soldier, desoldiering braid
* [Adeept starter kit](https://www.amazon.com/gp/product/B01GHVNP0M/)
* [Fisheye night-vision camera](https://www.amazon.com/gp/product/B06XNV5R6T/)
* [Solid hook-up wire kit - 6 colors dispenser box](https://www.amazon.com/gp/product/B008L3QJAS/)
* [25rpm 12V DC worm gear motor](https://www.amazon.com/gp/product/B01N1JQFYX/)

(continued below)


* [0.3A glass fuse & holder](https://www.amazon.com/gp/product/B01FWR2R38/)
* [bag o' hall effect (magnetic) sensors](https://www.amazon.com/gp/product/B00ATNJH20/)
* [bag o' test leads (wires with alligator clips at ends)](https://www.amazon.com/gp/product/B0002KRABU/)
* [SanDisk Ultra 32GB microSDHC UHS-I Card](https://www.amazon.com/gp/product/B010Q57T02/)
* [12VDC 600mA regulated power supply](https://www.sparkfun.com/products/9442)



# Thank you!

* Blog <http://adammonsen.com>
* Email <haircut@gmail.com>

SpeakerNote: I want to hear what works for you or what I could do better.
Please let me know!
