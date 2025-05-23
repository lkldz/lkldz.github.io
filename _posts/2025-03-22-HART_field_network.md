---
title: HART introduction - Field Network.
date: 2025-03-22 10:10:00 +100
categories: [Industry_Automation, HART]
tags: [HART, Industry_Automation]
---

# <span style="color:olive">What is a Field Network?</span> 
---

### <span style="color:orange">Field Network Concept</span> 

- A field network, is also known as a fieldbus network, 

- is a <b>communication system</b> used in industrial automation <b>to connect various field devices, such as sensors</b>, actuators, and controllers, <b>to a central control system</b>. 

- it <b>allows these field devices to communicate with each other and with higher-level control systems, enabling efficient monitoring and control of industrial processes</b>.

### <span style="color:orange">Field Network Components</span> 
#### <span style="color:gray">Field Devices</span> 
These are the <b>devices located in the field (i.e., the industrial environment) that perform specific tasks</b>. 

Examples include:
- sensors (which measure temperature, pressure, etc.), 
- actuators (which control valves, motors, etc.), 
- and controllers (which process data and make decisions).

#### <span style="color:gray">Communication Protocol</span> 
<b>A set of rules and standards that define how data is transmitted and received over the network</b>. 

Common fieldbus protocols include:
<ul> 
    <li>PROFIBUS,</li> 
    <li>Modbus,</li> 
    <li>HART,</li> 
    <li>Foundation Fieldbus.</li>
</ul>

#### <span style="color:gray">Network Topology</span> 
<b>The physical and logical arrangement of devices on the network.</b>. 

Common topologies include:
<ul> 
<li>bus,</li> 
<li>star,</li> 
<li>ring,</li> 
<li>tree</li>
</ul>

#### <span style="color:gray">Central Control System</span> 
<b>The system that monitors and controls the field devices.</b>. 

It can be:
<ul> 
<li>a programmable logic controller (PLC),</li> 
<li>a distributed control system (DCS),</li> 
<li>a supervisory control and data acquisition (SCADA) system</li> 
</ul>

![localImage](/assets/images/industry_automation/field_network_structure.png)

[Source of the image](https://www.ia.omron.com/support/guide/23/introduction.html)


### <span style="color:orange">How a Field Network Works</span> 
#### <span style="color:gray">Data Collection</span>
Sensors in the field collect data from the industrial process (e.g., temperature, pressure, flow rate) and send this data to the central control system over the field network. 

#### <span style="color:gray">Data Processing</span>
The central control system processes the data received from the sensors. It may use this data to make decisions, such as adjusting the position of a valve or changing the speed of a motor.

#### <span style="color:gray">Control Actions</span>
Based on the processed data, the central control system sends commands to actuators in the field to perform specific actions (e.g., opening a valve, starting a motor).

#### <span style="color:gray">Feedback Loop/Controls</span>
The system continuously monitors the process, collects data, processes it, and sends control commands, creating a feedback loop that ensures the process operates efficiently and safely.

![localImage](/assets/images/industry_automation/feedback_controls1.png)

[Source of the image](https://www.britannica.com/technology/automation/Feedback-controls)

![localImage](/assets/images/industry_automation/feedback_controls2.png)

[Source of the image](https://www.electronics-tutorials.ws/systems/closed-loop-system.html)


### <span style="color:orange">Benefits of Field Networks</span>
#### <span style="color:gray">Reduced Wiring</span>
Field networks reduce the amount of wiring needed compared to traditional point-to-point wiring, as multiple devices can share the same communication bus.

#### <span style="color:gray">Improved Data Accuracy</span>
Digital communication reduces the risk of signal degradation and interference, leading to more accurate data transmission.

#### <span style="color:gray">Enhanced Diagnostics</span>
Field networks often include diagnostic capabilities that allow for real-time monitoring of device status and network health, making it easier to detect and troubleshoot issues.

#### <span style="color:gray">Scalability</span>
Field networks can easily be expanded by adding more devices to the network without significant changes to the existing infrastructure.

### <span style="color:orange">Example</span>

![localImage](/assets/images/industry_automation/example_field_network1.png)

[Source](https://zipautomations.com/2024/07/31/abb-800xa-dcs-system-architecture/)

<b>Level: Field Network</b> - field devices send the signals to the controllers via predefined signals (24V, 4-20mA) according to fieldbus protocols, like HART, PROFIBUS, Modbus etc.

<b>Level: Control Network</b> - on this level there is communication between controllers on the network.
The controllers share information about its variables like (transmitter values, power parameters etc) with other controllers on the network.
On this layer different communication protocols like HART, PROFINET, PROFIBUS, MODBUS etc. can be used for communication.
The control network is also used for communication between the controllers or DCS servers (the main purpose of the servers is to acquire information from the control network for logging, analysis, visualization and so on).

<b>Level: Client Server Network</b> - used for communication between DCS servers and the operator workplace for visualization. AND also, between the servers and the engineering workplace for controller programming and tag configuration. The protocol most used here is OPC and for newer systems OPC UA.

<b>Level: Plant Network</b> - used for communication between the control system and the plant IT/Business Systems.

### <span style="color:orange">Next examples</span>


1.A field network in which the control data of systems and equipment on the line and the data of sensors that detect the state of works in progress and other information is exchanged with a programmable logic controller (PLC). [Source](https://article.murata.com/en-global/article/dx-smart-factory-7)
![localImage](/assets/images/industry_automation/example_field_network2.png)

2.Typical Architecture of Computer Control Systems by Schneider Electric-Modicon Quantum PLC. [Source](https://www.researchgate.net/figure/Typical-Architecture-of-Computer-Control-Systems-Source-Schneider-Electric-Modicon_fig3_315771543)
![localImage](/assets/images/industry_automation/example_field_network3.png)