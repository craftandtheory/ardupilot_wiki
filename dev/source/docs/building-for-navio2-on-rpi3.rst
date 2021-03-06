.. _building-for-navio2-on-rpi3:

===========================
Building for NAVIO2 on RPi3
===========================

Overview
========

These instructions clarify how to build ArduPilot for the Navio2 board
on the Navio2's RPi3 board itself using Waf build system. These instructions assume the RPi3
has already been setup according to the manufacturer's (i.e. Emlid's)
instructions
`here <http://docs.emlid.com/navio2/Navio-APM/configuring-raspberry-pi/>`__.

Alternatively you can follow Emlid's instructions on how to build from
source found
`here <http://docs.emlid.com/navio2/Navio-APM/building-from-sources/>`__.

Setup
-----

Use an ssh terminal program such as `Putty <http://www.putty.org/>`__ to
log into the Navio2 board's RPI3.

Clone the source:

::

    git clone https://github.com/diydrones/ardupilot.git
    cd ardupilot
    git submodule update --init

.. note::
    
    Waf should always be called from the ardupilot's root directory.


To keep access to Waf convenient, use the following alias from the root ardupilot directory:

::
    
    alias waf="$PWD/modules/waf/waf-light"

Choose the board to be used:

::

    waf configure --board=navio2

Build
-----

Now you can build arducopter. For copter use the following command:

::

    waf --targets bin/arducopter


To build a helicopter, specify "arducopter-heli".
The following frame types are specified in the "Frame Type" item of the Mission Planner menu "INITIAL SETUP".

::

    Quad Hexa Octa Octa-Quad Y6  Heli Tri

In the end of compilation binary file with the name arducopter will be placed in ``ardupilot/build/navio2/bin/ directory``.


