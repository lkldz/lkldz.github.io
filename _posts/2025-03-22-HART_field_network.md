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