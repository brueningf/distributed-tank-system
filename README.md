# Distributed Tank System

The **Distributed Tank System** is a modular IoT platform for monitoring and controlling multiple fluid tanks.  
Originally developed as a prototype for research and educational purposes, it has also been applied in practice to manage water tanks for a house installation.  

The system consists of distributed **sensor/actuator nodes**, a **central controller**, and a **dashboard app**. While this implementation focuses on water management, the architecture is adaptable to other fluids and use cases.  

Development took place in rural Peru, emphasizing **low-cost, low-power components** and **wireless communication**. Some documentation and comments may appear in Spanish.  

The system is designed to be **scalable**: additional modules can be integrated, with the controller coordinating logic across the network. The dashboard app provides real-time data visualization and debugging.  

Fancy control modes are under development, with automatic operation currently functional.
Errors were made, and some design choices are suboptimal, so revisions were made along the way. Feel free to ask questions, or **browse through the photos in docs/images** for more context.

---

## Overview

This project demonstrates a distributed embedded system where multiple nodes communicate with a central controller.  
Each **node** measures tank conditions (e.g., liquid level) and reports to the **controller**, which manages logic and communication with the **dashboard app**.  
Redundancy in sensors and actuators ensures reliability.

### Features
- Modular architecture: additional tank nodes can be added.
- Wireless communication for nodes, adding flexibility for placement.
- Centralized controller for system logic and communication.  
- Robust electrical design for outdoor use, and semi-industrial environments.
- Temperature, humidity, and ambient pressure sensing for environmental monitoring, and future maintenance features.
- Dashboard app for real-time monitoring and debugging.  
- In-progress: control modes and extended features.  

---

## System Architecture

![System Overview](docs/images/functional-schema-revised.jpeg)

The architecture consists of:
- **Nodes**: Independent modules with sensors/actuators, implemented in Toit.  
- **Base Controller**: Central unit, implemented in Toit, coordinating nodes and serving data to the app.  
- **Dashboard App**: Kotlin application for visualization and debugging.  

Communication between components is currently based on [Wi-Fi, HTTP].

---

## Photos

**Base controller**  
![Base Controller](docs/images/base1_working.jpeg)  
![Base Controller Schematic](docs/images/base-schematic-revised.jpeg)  
![RWI Schematic](docs/images/rwi-schematic2.jpeg)  

**Water system and sensors**  
![Water System](docs/images/fluid-system-labeled.jpeg)  

**Example node**  
![REMST2](docs/images/remst2-working.jpeg)  
![REMST2 schematic](docs/images/remst2-schematic-revised.jpeg)  

**Installation in Peru**  
![Base Controller Installation](docs/images/installation1.jpeg) 

---

## Some videos

[PCB assembly](https://youtube.com/shorts/jMC6awK2nHs)

[REMST2 PCB layout](https://youtu.be/X4QR3ed8DRU)  

---

## Repository Structure

distributed-tank-system/
│-- dashboard/ # Kotlin dashboard app
│-- system/ # Toit code (firmware for nodes and controller)
│-- docs/ # Images, diagrams, extra documentation

---

## Technology

- **Hardware**: custom PCBs, ESP32, pressure sensors, pumps, valves, flow sensors, and other components.
- **Embedded Software**: C++, Espressif firmware, Toit  
- **Dashboard App**: Kotlin (Android)  
- **Communication**: Wi-Fi, HTTP (MQTT planned)
- **Development Tools**: Toit SDK, Android Studio, old CAD software for PCB design, many other tools.

---

## Current Status

- Real-time monitoring and debugging through dashboard app – completed  
- Modular node design – completed  
- Controller logic for node coordination – completed  
- Control modes – in progress  
- Additional features (alerting, optimization, remote access) – planned  

Although the system is functional, it is a prototype and may require further refinement for production use.

---

## Future Work

- Implementation of more modes for maintenance, manual, and automatic control.
- Scaling to larger numbers of nodes.  
- Integration of additional sensor types, and AI/ML for predictive maintenance.
- Exploring security and reliability in distributed IoT systems.  

---

## License

This project is licensed under the Apache License 2.0.  
You may obtain a copy of the License at [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0).

