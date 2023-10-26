# Abstracting the Board

Before controlling matter, you need to understand it, abstract it effectively and find a way to actuate the abstractions. The naming does not matter, only the intention of the abstraction is what matters.

**PAC (Peripheral Access Crate)**   
This library abstracts the registers and MMIO memory addresses in an intuitive way.  
It may present the Registers as structs with sensible names, you do not have to worry about accessing addresses using hexdecimal notations and perform raw pointer operations... this makes your code more portable.    
This crate does not expose functionalities of the hardware, it just gives you access_variables and the different methods of accessing and manipulating those access variables.  

**Micro-architecture Crate**    
This crate abstracts the micro-controller itself. (Without the board). It abstract things like the ISA implementation, the inbuilt circuits like Timer, Interrupt controller, FPU, extensions.  

This crate is as low-level as the PAC... it is just the PAC abstracts peripherals while the MAC(Micro-architecture Crate) abstracts the MCU and its inbuilt circuits.   

Additionally, unlike the PAC, it exposes the different functinalities of the MCU such as interrupt handling mechanisms. 

MACs are typically provided by the MCU manufacturers


**HAL (Hardware Abstraction Layer)**   
This crate exposes the generic API for a piece of peripheral. It exposes functionality. It uses the PAC and MAC libraries as its building blocks.  
The HAL is more generic than the MAC and PAC crates.    

For example, if we had the UART as our piece of hardware, then the PAC will expose the address 0x200_000 as the FIFO control register. The HAL register will then use that register variable to build the 'enable FIFO' function.  

**Peripheral Driver Crates**    
This crate is a highly specific HAL for a certain piece of hardware/perioheral. This is no longer a generic HAL...it is a generic HAL + other new fuctionalities that are manufacturer-unique

**Board Crate**  
The board crate goes a step further at being ALL-encompassing. It tries to abstract the whole development board by combining the relevant PACs, MACs, HALs and Driver crates into one crate.  

**Utility Crates**  
These crates may not directly interact with hardware but provide utility functions and data structures that can be helpful in embedded development. For example, crates for working with fixed-point arithmetic, bit manipulation, or data serialization.
