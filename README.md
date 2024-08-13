## About This Repository
This repository is a detailed example application how to use the [CHALET_Xts](https://github.com/Beckhoff-Switzerland/CHALET_Xts) framework
![TcXtsViewer_AWOcoVZ6J1](https://github.com/Beckhoff-Switzerland/CHALET_Xts_Example/assets/143804651/733ba5a4-3014-4a61-944e-9c7119c26870)

The main features of this example application are : 
- 100 individually controllable XTS movers
- Perimeter of 21 metres
- 24 individually configurable stations with a logic similar to a rotary indexing table 
- The 'external' process at each station can access each mover in the station to e.g. read/write product data and decide where the mover should go next.
- Easily configurable simulation mode to simulate a process and detect bottlenecks at an early stage without hardware
- Changing the mover dynamics on different sections of the track


### There are three types of stations that can be freely placed:<br>
  ${\color{blue}Blue}$ - Dynamic changes and gap of passing movers. e.g. to travel slower in the curve and with a larger gap<br>
  <img src="https://github.com/Beckhoff-Switzerland/CHALET_Xts_Example/assets/143804651/086499c9-d124-47c2-bf69-260efc10256a"  height="100"><br>
  
  
  ${\color{green}Green}$ - Waiting station that is automatically approached if the next station is already full.<br>
  <img src="https://github.com/Beckhoff-Switzerland/CHALET_Xts_Example/assets/143804651/04142fb2-5017-4702-ac05-c30f2e53daa9"  height="100"><br>
  
  
  ${\color{red}Red}$ - Actual processing station<br>
  Gives a signal to the process as soon as all movers are present. Receives a signal from the process as to where the movers should go next. In Simulation mode, a process time can be simulated here.<br>
  <img src="https://github.com/Beckhoff-Switzerland/CHALET_Xts_Example/assets/143804651/cce19d9f-6bc0-41e8-8653-ab03eee83534"  height="100"><br>


---
## Requirements
- [TE1000 | TwinCAT 3 Engineering](https://www.beckhoff.com/en-en/products/automation/twincat/texxxx-twincat-3-engineering/te1000.html)
- [TF5850 | TwinCAT 3 XTS Extension](https://www.beckhoff.com/en-en/products/automation/twincat/tfxxxx-twincat-3-functions/tf5xxx-motion/tf5850.html)
- [TF5410 | TwinCAT 3 Motion Collision Avoidance](https://www.beckhoff.com/en-en/products/automation/twincat/tfxxxx-twincat-3-functions/tf5xxx-motion/tf5410.html)

---
## Quick Start
When the project is opened in TwinCat for the first time, certain PLC libraries are missing. These are stored in the project and can be installed using the following button.<br>
![image](https://github.com/Beckhoff-Switzerland/CHALET_XPlanar_Example/assets/143804651/2eaaeeea-066d-446c-9530-650616aed40e)<br>

Scan existing CPU cores and select an isolated one for code execution<br>
![image](https://github.com/Beckhoff-Switzerland/CHALET_XPlanar_Example/assets/143804651/2a9a3c79-fef8-45c8-b2de-12903479d375)<br>

Download and login to the PLC
Navigate to the main program. As soon as the system reports back that it has been initialized, bEnable can be toggled. 
