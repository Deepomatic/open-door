## Goal

The goal of this tutorial is to be able to open the door of our building thanks to our smart-phone. We will use a [Raspberry](https://www.raspberrypi.org/) and some electronics to setup a web server and link it to our intercom. The installation will eventually look like this:

![installation](install.jpg)

## Software installation

Just run the following on your Raspberry:
```
apt-get update
apt-get install -y make git sudo python g++
git clone https://github.com/Deepomatic/open-door.git
cd open-door
make
make install
```

This will start a django server that will expose the following URL: [http://localhost/door/open](http://localhost/door/open). To open the door, just visit this URL. Don't forget to password-protect it ! ;-)

## Raspberry Pi

We use [WiringPi](http://wiringpi.com/) to control the pins of the Raspberry. The mapping between physical pins and WiringPi pin IDs is as follows:

![pin mapping](http://wiringpi.com/wp-content/uploads/2013/03/gpio1.png)

We will use **GPIO0** to send the door opening signal and the **GND** (**0v**) next to it, aka the pins with headers 11 and 9, respectively.

The wiring will thus look like this:

![close-up](close_up.jpg)

## Circuit

You need:
- 1 NPN Transitor with 200 gain
- 1 Resistor of 14 kohms

The circuit is the following:

![circuit](circuit.jpg)
