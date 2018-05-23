---
---

# Notice
This page is currently being developed. Expect changes and additional information in the coming weeks.

![Twirre test platform, 2017][twirre_header]

## Introduction
TBA

## Contents

* [Architecture overview](#architecture-overview)
* [Software components](#software-components)
* [Hardware components](#hardware-components)
* [Licensing](#licensing)
* [Demo pictures and videos](#demo-pictures-and-videos)
* [About us](#about-us)

## Architecture overview
TBA

## Software components
Several software components have been created for use with the Twirre architecture:

* [TwirreLink](#twirrelink)
* [TwirreArduino](#twirrearduino)
* [TwirreLogReader](#twirrelogreader)
* [Additional sensor libraries](#additional-sensor-libraries)

This page will only give a short summary for these components. Please check the corresponding repositories for more detailed information.

#### TwirreLink
The TwirreLink library provides a generic sensor / actuator communication API. It is considered to be the core of the Twirre architecture. TwirreLink also contains TwirreSerial, a protocol for communication over serial links, which is used to add sensors and actuators connected to an Arduino DUE to TwirreLink. The library is (mostly) thread-safe, and has a built-in asynchronous logging system.

Repository: <https://github.com/NHLStenden-CVDS/TwirreLink>

#### TwirreArduino
TwirreArduino is an Arduino sketch compatible with the Arduino DUE. It provides communication with several sensors and actuators, and is compatible with the TwirreSerial protocol allowing these devices to be used on the host computer through TwirreLink.

Repository: <https://github.com/NHLStenden-CVDS/TwirreArduino> 

#### TwirreLogReader
A quick-and-dirty Python file for parsing TwirreLink logs.

Repository: TBA

#### Additional sensor / actuator libraries
Some additional TwirreLink-compatible libraries have been written for communication with specific sensors. 

Repository: TBA
 

## Hardware components
TBA

## Licensing
MIT license applies to all Twirre software and hardware schematics

## Demo pictures and videos
TBA

## About us
TBA: Info about the NHL Stenden University of Applied Sciences - Centre of Expertise in Computer Vision & Data Science





[twirre_header]: images/index/twirre_header.jpg

