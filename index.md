---
---

![Organisation logo][nhlstenden_cvds_logo]

# Notice
This page is currently being developed. Expect changes and additional information in the coming weeks. **All text must be considered to be concept text only.**

![Twirre test platform, 2017][twirre_header]

# Summary

Twirre is a flexible architecture for autonomous vehicles using low-cost and interchangeable commodity components. Its initial development platform has been a drone, but the architecture is also suitable for other types of vehicles such as (model)boats and ground vehicles. Several software components have been developed for Twirre, including TwirreLink, a sensor/actuator communication library, and TwirreArduino, which allows an Arduino DUE to be used for sensor/actuator communication. TwirreArduino can also communicate with an instance of TwirreLink running on a main computer through USB. These software components can be used on Windows and Linux (tested on Ubuntu), and have been used on both x86-AMD64 based computers and ARMv7- or ARM64-based computers. 

Twirre also encompasses a generic hardware architecture. Reference hardware for the current testing platform will also be detailed. Finally, a PCB design with components list is provided for a 'shield' for the Arduino DUE, which provides a cleaner way of connecting various sensors to the microcontroller.

Twirre has been designed and developed by the Leeuwarden (the Netherlands)  - based [NHL Stenden University of Applied Sciences][nhlstenden-site]'s [Centre of Expertise in Computer Vision & Data Science][cvds-official-site]. The software is provided under MIT license, and can thus be used easily in both open-source and commercial projects. It is kindly requested to share any useful modifications and additions to Twirre software, for the benefit of all who are (planning to) use this software.

# Contents

* [Introduction](#introduction)
* [Architecture overview](#architecture-overview)
* [Software components](#software-components)
* [Hardware components](#hardware-components)
* [Licensing](#licensing)
* [Demo pictures and videos](#demo-pictures-and-videos)
* [About us](#about-us)

# Introduction
In recent years, the usage of drones (or, more generally, Remotely Piloted Aircraft Systems ('RPAS')) has been massively expanding. Increasingly affordable and capable small multirotor aircraft have become available. For the field of computer vision, this provides a new way of collecting image data from the air. Drones can for example be used to collect detailed, high-resolution data of agricultural fields for advanced crop health analysis. However, the distance between pilot and aircraft, together with inherent limits of human pilots, presents a limit on the usability of drones for detailed inspection. 

For example, inspection of windmill turbine blades for damage requires very high resolution images, which can only be taken from a short distance. This is currently done by an inspector climbing the windmill and manually taking pictures of potential problems using a high-end handheld photo camera. Performing such an inspection using a drone would be much safer and more cost-effective. Some attempts have been made to do this with standard RPAS systems with a DSLR camera attached, but the image quality achieved in that way is generally insufficient due to the pilot not being able to safely fly close enough to the windmill blade. For these kinds of missions, an autonomous drone would be required. That way, the drone can automatically fly at the required distance using distance information from for example depth camera, ultrasonic, or (2D/3D) LiDAR sensors. The drone could perhaps also automatically trace the edges of the windmill blade, ensuring the full surface is captured on camera.

So far, some basic forms of autonomy in drones have become available commercially. This includes, for example, automatic GPS waypoint flight, basic collision avoidance, and target/POI following. For the type of missions described above these are insufficient. Also, that functionality is typically deeply integrated into commercial drones or components, and cannot be adjusted, modified or extended for more advanced purposes.

Some more advanced experiments/research/projects have been published with regards to autonomous control of drones. However, these generally present some other issues:

* #### Autonomous functionality is often directly integrated into the low-level flight controller
This makes it more difficult to correct for errors in the autonomous control (especially software bugs causing crash of the flight controller). Also, such functionality is poorly transferable to different models of flight controllers, such as improved models, different drone models, or other types of vehicles.

* #### Relying on external equipment
   A lot of very impressive demos have been made in specially-equipped rooms with for example an array of cameras attached to the ceiling, allowing fast and accurate determination of the drone's position and orientation. Although this provides a fairly easy solution to one of the bigger problems of autonomous flight, it means the vehicle cannot easily be used in new locations and severely limits its practical applications.

   Similarly, a remote computer is sometimes used to perform the required sensor processing and control logic. This allows a more powerful computer to be used, but also presents limitations due to the required wireless communication link, with limited bandwidth, increased latency, and packet loss or even complete loss-of-link. It also somewhat complicates transportation and deployment of the complete system, increasing mission cost. As such, an on-board computer would be preferrable.

In order to facilitate experiments for more advanced autonomous flight, the NHL Stenden Centre of Expertise in Computer Vision & Data Science has decided a couple of years ago to develop a flexible architecture for autonomous mini-UAVs using interchangeable commodity components: the Twirre architecture. Development started as a small in-house project mainly by internship students, but it has since scaled up to subsidised commercial proof-of-concept projects. During development it was also realised that the Twirre architecture is not limited to UAVs, but can also easily be adapted for other types of vehicles. Subsequently, a project for development of an autonomous model boat has also been started.


# Architecture overview
TBA

# Software components
Several software components have been created for use with the Twirre architecture:

* [TwirreLink](#twirrelink)
* [TwirreArduino](#twirrearduino)
* [TwirreLogReader](#twirrelogreader)
* [Additional sensor libraries](#additional-sensor--actuator-libraries)

This page will only give a short summary for these components. Please check the corresponding repositories for more detailed information.

### TwirreLink
The TwirreLink library provides a generic sensor / actuator communication API. It is considered to be the core of the Twirre architecture. TwirreLink also contains TwirreSerial, a protocol for communication over serial links, which is used to add sensors and actuators connected to an Arduino DUE to TwirreLink. The library is (mostly) thread-safe, and has a built-in asynchronous logging system.

Repository: <https://github.com/NHLStenden-CVDS/TwirreLink>

### TwirreArduino
TwirreArduino is an Arduino sketch compatible with the Arduino DUE. It provides communication with several sensors and actuators, and is compatible with the TwirreSerial protocol allowing these devices to be used on the host computer through TwirreLink.

Repository: <https://github.com/NHLStenden-CVDS/TwirreArduino> 

### TwirreLogReader
A quick-and-dirty Python file for parsing TwirreLink logs.

Repository: <https://github.com/NHLStenden-CVDS/TwirreLogreader>

### Additional sensor / actuator libraries
Some additional TwirreLink-compatible libraries have been written for communication with specific sensors. These are currently bundled in a single repository.

Repository: <https://github.com/NHLStenden-CVDS/TwirreLinkAddons>
 

# Hardware components

* [UAV test platform hardware info](#uav-test-platform-hardware-info)
* [twirreshield](#twirreshield)

### UAV test platform hardware info

TBA


### TwirreShield
Design for a sensor/actuator interface shield for the Arduino DUE.

Repository: <https://github.com/NHLStenden-CVDS/TwirreShield>


# Licensing
MIT license applies to all Twirre software and hardware schematics

# Demo pictures and videos
TBA

# About us
TBA: Info about the NHL Stenden University of Applied Sciences - Centre of Expertise in Computer Vision & Data Science




[nhlstenden_cvds_logo]: images/index/nhlstenden_cvds.png
[twirre_header]: images/index/twirre_header.jpg

[nhlstenden-site]: https://www.nhlstenden.com/en
[cvds-official-site]: https://onderzoek.nhl.nl/en/lectorships/computer-vision
