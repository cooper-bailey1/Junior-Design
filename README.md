# Junior Design

## Overview

This repository contains the code for the Mac Jones Group Junior Design project. It serves as the primary code base for system development, hardware bring-up, and feature implementation. The project is built using PlatformIO and runs on an Arduino WiFi Uno targets an embedded microcontroller platform, with all firmware written in C++ and C.

## Hardware Overview

The firmware in this repository is designed to run on a microcontroller based embedded system developed as part of the Junior Design project. The hardware platform includes a primary MCU responsible for system control, communication, and peripheral management.

Key hardware components supported by this firmware include:

- A microcontroller configured using PlatformIO
- Digital and analog I/O peripherals
- External modules and sensors interfaced through standard communication protocols such as I2C and GPIO toggling
- On-board debugging and programming support

All hardware specific configuration, including pin mappings and peripheral initialization, is handled within the firmware source files and PlatformIO configuration.

### State Machine Architecture

The core application logic is implemented as a state machine. Each state represents a distinct mode of operation for the system, such as initialization, idle behavior, active control, or error handling.

State transitions occur based on inputs from the hardware and internal conditions, including:

- Sensor readings
- User inputs from a websocket
- Communication events
- Timing or timeout conditions

On each iteration of the main loop, the firmware checks relevant inputs and determines whether a state transition is required. When a transition occurs, the current state is updated, and the logic associated with the new state is executed. This structure ensures predictable control flow and makes system behavior easier to reason about, debug, and extend.

The state machine design allows new functionality to be added by introducing additional states or transitions without significantly restructuring existing code.

## Design Philosophy

The firmware is structured to prioritize readability, modularity, and ease of debugging. Interfaces are clearly defined through header files, and implementation details are isolated within source files. This approach supports incremental development and simplifies integration of new hardware features throughout the Junior Design project lifecycle.

## Authors

This repository is maintained by the Junior Design team, including:

- Cooper Bailey
- Jacob Gerson
- Asher Milberg
- Mason Doshi
