# PATRA: Parallel Axis TriTeron Robotic Arm

 **PATRA (Parallel Axis TriTeron Robotic Arm)** is an open-source robotic system developed by Sunrit Hazra as part of the Hack Club Forge program. The project combines a three-degree-of-freedom (3-DOF) parallel-axis mechanism, based on the TriTeron concept, with a six-degree-of-freedom (6-DOF) serial robotic arm.

 The system is designed to provide approximately 1 metre of linear movement while carrying a target payload of 2 kg. Unlike a conventional industrial seventh-axis system, which generally provides a single additional translational degree of freedom, PATRA uses a three-axis parallel mechanism to move the robotic arm across a larger workspace.

 The project focuses not only on the final robot, but also on documenting the engineering process used to develop it. Its development records include mechanical design iterations, kinematic calculations, component selection, manufacturing constraints, sourcing decisions, and design-for-manufacturing (DFM) studies.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/595b11b4-895e-46de-bdb0-0ff063add276" />

 ## System architecture

 PATRA is divided into three principal modules. This modular arrangement allows individual parts of the system to be designed, manufactured, and tested independently before final integration.

 ### Kinematic Base Module

 The **Kinematic Base Module (KBM)** forms the structural foundation of the robot. It provides the primary X and Y motion using a dual-axis arrangement approximately one metre in length.

 The axes use stacked GT5 timing belts driven by high-torque closed-loop stepper motors. Dual MGN15H linear guides are used to support and constrain the moving assemblies.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6ba5da5c-0a65-4ccb-80f5-f1cc7587e40d" />

 ### TriTeron Robot Module

 The **TriTeron Robot Module (TRM)** is the central parallel mechanism of PATRA. It provides three degrees of freedom through a system of mechanically linked members.

 The design uses custom linkages, 608ZZ ball bearings, and custom timing-belt clamping components. Particular attention was given to the stiffness of the pivot assemblies, since forces acting on the mechanism can introduce bending and positional errors in downstream components.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8f087050-faa8-4d84-91d0-df4aee05f3d5" />

 ### Robotic Arm Module

 The **Robotic Arm Module (RAM)** consists of a separate 6-DOF serial robotic arm mounted on the moving tool head of the parallel mechanism.

 The serial arm is intended to provide the orientation and fine positioning capabilities that are not provided directly by the three-axis parallel base. Final integration of this module is planned as a later stage of the project.

 ## Technical specifications

 The motion system was developed around commercially available components and standardized mechanical parts. The current configuration is as follows:

 | Parameter | X and Y axes | Z axis |
| --- | --- | --- |
| Drive system | Stacked GT5 timing belt | Stacked GT5 central loop |
| Linear guides | Dual MGN15H guides | Embedded carriage rail system |
| Motor | Rtelligent 57AM23ED, 2.3 N·m | Rtelligent 57AM30ED, 3 N·m |
| Motor driver | Rtelligent T60S | Rtelligent T60S |
| Pulley | 22-tooth GT5 | 20-tooth GT5 |
| Calculated centre distance | 1067.5 mm | 1202.5 mm |
| Closed-loop belt length | 449 teeth | 501 teeth |

The values represent the mechanical configuration developed during the design process and may change as fabrication and testing continue.

 ## Mechanical design

 A major consideration in PATRA's development was the balance between rigidity, cost, manufacturability, and availability of components.

 The original design considered the use of ball screws for linear movement. Ball screws were subsequently replaced by wide GT5/HTD timing belts. This reduced the mass and cost of the motion system while simplifying fabrication and sourcing.

 ### Belt-length optimisation

 The belt-driven architecture introduced a separate geometric constraint. Because the system uses closed-loop timing belts, the physical dimensions of the machine have to correspond to an integer number of belt teeth.

 During development, the nominal 1000 mm rail dimension was therefore adjusted in some areas to approximately 1001 mm. This allowed the calculated centre distances to correspond to commercially available closed-loop belt lengths without relying on excessive belt tensioning or custom clamping arrangements.

 The X and Y mechanisms use a 449-tooth belt loop, while the Z mechanism uses a 501-tooth loop.

 ## Materials and manufacturing

 PATRA was designed with small-scale manufacturing constraints in mind. Much of the development was carried out with the limitations of student-level fabrication and locally available components in India.

 Large structural housings were designed for fused deposition modelling (FDM) rather than relying exclusively on industrial manufacturing processes. PETG with carbon-fibre reinforcement was selected for several structural components where increased stiffness was desirable.

 For components subjected to higher loads or multidirectional stresses, the design uses industrial MJF-printed PA12 nylon. Custom belt-tooth locking components are an example of parts where this manufacturing method was considered preferable to conventional FDM printing.

 This approach allowed the design to use more expensive manufacturing processes selectively rather than applying them to the entire machine.

 ## Bearing and pivot design

 The linkages of the TriTeron mechanism use 608ZZ ball bearings in their pivot assemblies.

 The pivot arrangement was revised during development to improve rigidity and reduce unwanted movement. The current design uses three nested bearings together with Misumi MSB8 shoulder screws. The arrangement is intended to constrain the linkage while reducing the transmission of bending loads into downstream components.

 The pivot geometry was treated as a structural component rather than simply a rotational joint, since small amounts of play at these locations can become significant when propagated through the parallel mechanism.

 ## Kinematics and simulation

 Kinematic analysis forms a significant part of the PATRA development process. The geometry of the parallel mechanism requires the relationship between actuator movement and tool-head position to be considered as a coupled system rather than as three independent linear axes.

 Multiple kinematic configurations and structural arrangements are being evaluated during development. Stress and motion simulations are used to identify potential weaknesses before fabrication.

 The project documentation records changes to the mechanical geometry alongside the calculations that motivated them, allowing later versions of the design to be compared with earlier configurations.

 ## Development methodology

 The project follows an iterative engineering process rather than treating the initial CAD model as a final design.

 Design changes have been made in response to several factors, including:

 - component availability;
- manufacturing limitations;
- belt geometry;
- structural stiffness;
- material selection;
- cost;
- assembly requirements; and
- results from kinematic and structural analysis.

 This process is documented in the project's engineering journal. The journal records design changes, calculation errors, parameter revisions, fabrication difficulties, and other decisions made during development.

 ## Development roadmap

 PATRA is being developed in several stages:

 1. **Conceptual sourcing and kinematic layout**
2. **Kinematic Base Module geometry development**
3. **Kinematic and structural simulation**
4. **Fabrication of the KBM and TRM**
5. **Electrical system and controller PCB development**
6. **Integration of the 6-DOF robotic arm**

 The stages are intended to allow the mechanical platform to be tested independently before the more complex serial arm is integrated.

 ## Engineering documentation

 A central part of the project is its engineering journal, which is maintained alongside the design files.

 The journal documents the development process on a day-to-day basis, including changes to structural dimensions, corrections to calculations, modifications to the parametric CAD model, sourcing decisions, and manufacturing problems.

 The documentation is intended to make the project reproducible and to provide a reference for students and other developers interested in parallel robotic mechanisms and low-cost robotic manufacturing.

 ## Open-source development

 PATRA is intended as an open-source robotics project. Its documentation covers both the final design and the intermediate engineering work used to reach it.

 The repository is intended to contain the mechanical design files, calculations, manufacturing information, and development journal required to understand and reproduce the system.

 Further documentation is planned for installation and assembly procedures, software and hardware dependencies, manufacturing settings, a bill of materials, and the project's applicable open-source licences.

 ## Project status

 PATRA remains an actively developed project. The stated dimensions, payload, and performance characteristics represent the current design targets unless explicitly identified as experimentally verified results.

 The mechanical base and TriTeron mechanism are being developed as independently testable modules, with electrical integration and the final serial robotic arm planned for later stages.

 ## Credits

 PATRA was developed by **Sunrit Hazra** as part of the **Hack Club Forge** program.

 The project acknowledges **Dan Rudmin of Zaber Technologies** and **Rowan Hunt of Not An Engineer** for design discussions and foundational insights that influenced the development process.
