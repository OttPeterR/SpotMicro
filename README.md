# SpotMicro

My own personal build and implementation of the Spot Micro quadruped \
More info about the open source version can be found at their [website](https://gitlab.com/custom_robots/spotmicroai).

#### Table of Contents
1. [Parts](#parts)
1. [Assembly](#assembly)
1. [Electronics](#electronics)
1. [Software](#software)
1. [Simulation](#simulation)

## Parts
Parts list of all things needed. Acquire them from wherever you prefer.
- Raspberry Pi - I'm using a Zero W, but there are 3D chassis models that support a full sized Pi or an Nvidia Jetson
- 12x Servo Motors - MG996R High Torque (60-80$ total)
- Servo horns (these can be 3D printed if really needed)
- Servo Controller with i2c - PCA 9685 (< 10$)
- 2x 4,000 mAh LiPo Batteries - S2 or S3 connector, 50C or higher rating (25$ each)
- LiPo Charger - Match S2 or S3 connector, 1.5A minimum (20$)
- 3 Axis Gyro Accelerometer - MPU 6050 (10$)
- UBEC with 3A 5V output
- LCD Display 16x2 with i2c
- Rocker switch
- Breadboards
- Wires
- Soldering Iron + Solder
- Bunch of M3, M4, M5 screws and nuts


## Assembly
How to put together the larger physical peices. Basic routing of servo wires, but actual wiring will be in the [Electronics](#electronics) section.


## Electronics
Wiring the breadboards and getting the batteries to all work.


## Software
#### Have some operating system
I'm assuming youre RPi or Jetson is running something Debian based. I'm working off of a RPi Zero W. How to do this should be super easy to find in many locations.


#### Upgrade your swap space
The RPi Zero has only 512 MB of ram, that kinda sucks, so we'll bump up the swap to 2 GB

First disable swap:\
`sudo dphys-swapfile swapoff`

Then increase the amount of swap to be used by editing (with sudo) the file at `/etc/dphys-swapfile` to include `CONF_SWAPSIZE=2048`

Initialize the newly increased swap file:\
`sudo dphys-swapfile setup`

Start swap back up again:\
`sudo dphys-swapfile swapon`

#### Install ROS Kinetic

ROS is Robot Operating System. There are a lot of steps to this and it took my slow little Pi about 6 hours to run all of the compilation. Follow [their instructions](http://wiki.ros.org/ROSberryPi/Installing%20ROS%20Kinetic%20on%20the%20Raspberry%20Pi) and come back here. They warned about a few issues that could arrise, but I was lucky and did not encounter any of them. This is likely due to their patching and me using a clean install or Raspbian without putting anything else on it. YMMV.

## Simulation
Virtual simulation of the Spot Micro, no physical robot necessary.


