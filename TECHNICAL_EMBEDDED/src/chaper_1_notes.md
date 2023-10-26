# chapter_1_notes

An Embedded system is a system that has been purposefully built for a certain application. It is not a general purpose system.  
Though this view is not absolute.  

They deal with constrained environments, both hardware and software eg ;
1. slow cpus to save power
2. lack of support for certain peripherals.

[incant] Now with this constrained environment, the system might not support certain peripherals or certain software. Such a situation forces the developers to come up with really unique APIs. Can modular wasm solve anything here? What is the problem/  unique APIs kill the dream for a programmable world.  

JTAG - a physical interface to help you interact with the microprocessor using developmet tools like debuggers and testers


## Problems
1. Cross development is hard and somehow incomplete
   1. compiling
   2. testing 
   3. Debugging
2. dsds


## Random

Yes we are in IoT, but should that microwave be connected to the net?   
Which domains are dependent on IoT?  
Which domain has products that churn the market?    
Which domain is iteresting to you?  

## Domains
- **Industrial IoT (IIoT)**: Focuses on improving efficiency and automation in industries through sensors, data analytics, and connectivity. Examples include predictive maintenance in manufacturing and asset tracking in logistics.
- **Healthcare IoT**: Involves wearable devices, remote patient monitoring, and smart medical equipment to improve patient care and health outcomes.  
- **IoT in Energy Management:** Includes smart grids, energy monitoring systems, and devices to optimize energy consumption in homes, buildings, and industries.
- **Swarm contruction robotics** - Like Bill-E
- **IoT in Space Exploration**: Involves satellite communication, remote planetary exploration, and data collection from space-based sensors.
- **Millitary**

## Why Rust now?
- asm itegration
- wasm integration
- high level to be even be used in cloud applications... unlike C

## Communication 
- 
- Https 


# Discovery Book

SoC == microcontroller  
sensors ==> SoC ==> Actuators(implementors of code eg arms)  

SoC != General purpose Computer(eg rasberry-Pi). SoC is more specialized, might have lesser number of componets, less cost, less resource intensive.  
Power consumption. Most microcontrollers consume a fraction of the power of a full blown processor. For applications which run on batteries, that makes a huge difference. 


