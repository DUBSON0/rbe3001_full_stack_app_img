# Docker Image for WPI RBE3001 - Robotics Engineering

## Overview

This Docker image is specifically designed for students in Worcester Polytechnic Institute's (WPI) RBE3001 - Robotics Engineering course. It provides a pre-configured environment with:

- **Ubuntu 20.04 LTS** as the base operating system.
- **MATLAB R2021b** for advanced computational tasks, simulations, and data analysis.
- **Precompiled Dynamixel SDK** for controlling Dynamixel motors.

## Image Details

- **Base Image:** Ubuntu 20.04 LTS
- **MATLAB Version:** R2021b
- **Dynamixel SDK:** Precompiled for ease of use with Dynamixel actuators.

## Getting Started

### Prerequisites

- Docker installed on your system. If not installed, follow the installation guide for your OS from [Docker's official documentation](https://docs.docker.com/get-docker/).

### Pulling the Image

To use this image, you can pull it from GitHub Container Registry:

```bash
docker pull williamsobral1/rbe3001_stack:latest

### Enable the USB post

Use:

dmesg | grep ttyUSB

To locate which bus the robot arm is on, then replace the x with the bus and run:

sudo chmod a+rw /dev/ttyUSBx

### Running the Container

sudo docker run --privileged --device=/dev/ttyUSB -v /dev:/dev -p 5901:5901 -p 6080:6080 --shm-size=1024M ml:r2021b -vnc
