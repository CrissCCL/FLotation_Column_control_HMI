# 🧪 Flotation Column Control System – LabVIEW GUI

This repository documents the development of a **supervisory control and instrumentation system**
for a **pilot-scale column flotation process**, implemented as part of my
**Master’s thesis in Electrical Engineering (2018)**.

The project integrates **decoupled MIMO control using PID loops**, **industrial automation**,
**data acquisition**, and **graphical supervision**, representing an applied control solution
for mineral processing experimentation.


## 📂 Contents

- `/LabVIEW` → Main LabVIEW VI implementing the supervisory GUI and decoupled MIMO PID control

> ⚠️ Note: The repository includes the original LabVIEW VI for reference purposes.
> Execution requires legacy software, drivers, and hardware.


## 🎯 Project Overview

The system was designed to regulate and supervise two strongly coupled process variables:

- **Liquid level (h)** inside the flotation column  
- **Gas holdup ($$\varepsilon_g$$)**  

using a **decoupled MIMO control structure**, implemented as
independent **PID control loops** after interaction analysis.

Real-time visualization, supervision, and actuation were achieved
through industrial communication and laboratory instrumentation.



## 🏗️ System Architecture

<p align="center">
  <img alt="System Architecture" 
       src="https://github.com/user-attachments/assets/3d8994f2-fd79-4b2a-a2fb-cdf094a75ed6" 
       width="400">
  &nbsp;&nbsp;&nbsp;
  <img alt="Copper Column Flotation Process" 
       src="https://github.com/user-attachments/assets/ea4d3a94-cece-44e6-a857-b4e03b76e9bc"
       width="450">
</p>


The pilot-scale experimental setup corresponds to a **column flotation process
for copper extraction**, providing the physical context for the control
architecture shown above.


High-level architecture of the control system:

- **Supervisory layer:** LabVIEW GUI (control, visualization, logging)  
- **Control & actuation:** PLC Siemens S7-1200  
- **Communication:** OPC server (LabVIEW ↔ PLC)  
- **Instrumentation:** NI USB-6002 DAQ  
- **Process:** Pilot-scale flotation column  

This architecture enabled real-time interaction between laboratory
instrumentation and industrial automation components.



## 🔁 Control Strategy (Decoupled MIMO)

<p align="center">
  <img alt="Decoupled MIMO Control Diagram" src="https://github.com/user-attachments/assets/78a452f5-2ff9-42f5-bc37-3f9153bfea06" width="500">
</p>

### Process Variables Definition

The following variables are used in the control block diagram:


- $$h$$: Pulp level inside the flotation column
- $$Q_p$$: Pulp flow rate (manipulated variable for level control)
- $$Q_g$$: Gas flow rate (manipulated variable for gas holdup control)
 $$\varepsilon_g$$: Gas holdup (gas phase volume fraction)

The system is modeled as a **2×2 MIMO process** with:

- Inputs: $$Q_p$$ ; $$Q_g$$
- Outputs: $$h$$ ; $$\varepsilon_g$$

Interaction between the loops motivated the use of a **decoupled control structure**.

The implemented control strategy consists of:

- Interaction analysis of the MIMO process  
- Decoupling of the control structure  
- Independent **PID controllers** for:
  - Liquid level  
  - Gas holdup  
- Continuous-time PID tuning implemented in LabVIEW  
- Actuation through **peristaltic pumps** driven by the PLC  

This approach simplifies controller design while preserving acceptable
performance under experimental operating conditions.

The decoupling strategy was guided by the interaction analysis obtained
from the preliminary modeling stage.


## 🖥️ Graphical User Interface

<p align="center">
  <img alt="GUI Running" src="https://github.com/user-attachments/assets/89bcbd90-3f52-4bcd-8f08-f3eb902f2560" width="550">
</p>

The LabVIEW-based GUI provides:

- Real-time visualization of process variables  
- Manual and automatic (PID) operation modes  
- Independent setpoint adjustment for each control loop  
- Monitoring of control signals  
- Data acquisition and logging  

The interface was developed for experimental usability
and process supervision rather than commercial HMI deployment.


## 🧪 Pilot-Scale Experimental Setup

<p align="center">
  <img alt="Pilot-Scale Flotation Column" src="https://github.com/user-attachments/assets/c1b67d15-f5aa-41c9-b9fb-4edf52aebc0c" width="500">
</p>

The control system was validated on a **pilot-scale flotation column**,
allowing:

- Experimental testing of decoupled MIMO control strategies  
- Observation of interaction effects and disturbance rejection  
- Integration of sensing, control, and supervision in a real process environment  

This confirms the applied and experimental nature of the work beyond simulation.



## 🧩 Hardware & Software

### Hardware
- Siemens **S7-1200 PLC**
- **NI USB-6002** Data Acquisition Card
- Peristaltic pumps
- Level and gas holdup sensors
- Pilot-scale flotation column

### Software
- **LabVIEW 2013**
- OPC server for PLC communication
- Decoupled MIMO PID control and data visualization implemented in LabVIEW

> ⚠️ Note: Due to legacy software and hardware dependencies,
> this repository is provided mainly for **documentation,
> reference, and demonstration purposes**.



## 📄 Related Publication

This work is associated with the following conference publication:

## 📄 Related Publication (Preliminary System Modeling)

The following conference publication presents a **preliminary dynamic modeling** of the flotation column system.
https://ieeexplore.ieee.org/document/8609809/

The publication describes the experimental setup,
MIMO interaction analysis, control strategy,
and main results obtained during the thesis work.

The publication focuses on:
- Preliminary dynamic modeling of the flotation column  
- Qualitative and quantitative analysis of variable interaction  
- Identification of the MIMO nature of the process  

The model should be understood as a **first-order and second approximation**
intended to support interaction analysis and control structure selection.

The **control strategy and supervisory implementation** documented in this repository
were developed based on this preliminary modeling and subsequent experimental insight,
and are **not covered in the paper itself**.

## 📌 Context

This project was developed during my **Master’s thesis (2018)**
and reflects an applied approach to:

- MIMO process control and decoupling  
- Industrial automation  
- Instrumentation and data acquisition  
- Experimental validation in mineral processing  



## ⚠️ Disclaimer

This repository is shared for **educational and documentation purposes only**.
It represents an experimental system developed in an academic context and is
**not intended for direct industrial deployment** without proper engineering
validation, safety analysis, and compliance with applicable standards.



## 🤝 Support Projects

Support my work on Patreon:  
https://www.patreon.com/c/CrissCCL


## 📜 License

MIT License
