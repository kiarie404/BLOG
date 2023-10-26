# RAM

RAM, which stands for Random Access Memory, is a type of volatile computer memory that serves as the primary working storage for data and program instructions that a computer's CPU (Central Processing Unit) can access quickly.

The RAM is made up of **memory Cells**. 

**Address Lines and Data Lines**: RAM chips have address lines and data lines that connect them to the CPU and other parts of the computer. The address lines are used to select specific memory cells, while the data lines transfer data in and out of RAM.

Overally a combination of the memory cells and the Address and Data lines form an Integrated Circuit

## DRAM vs SRAM
Before discussing DRAM vs SRAM, Let's first get some buzzwords out of the way.    
#### 1. Transistor 
A **semiconductor** is a type of material that has electrical conductivity properties between those of conductors (such as metals) and insulators (such as non-metals). Semiconductors are characterized by their ability to conduct electricity under certain conditions but not others, making them crucial components in the field of electronics. Examples of semiconductors include Silicon and Gallium Asenide.   

To make a semiconductor become more conductive, you change its structure through a process called n-type doping. Doping can be done by adding an impurity like phosphorous to the silicon. But in modern computers, instead of conducting hemical reactions, the silicon structure is changed through ion implantation. My knowledge ends there... research on your on. i ain't reading that.  

To reduce the conductivity, yiou still use that ion implantation  black-box magic.  

A transistor acts as a switch and amplifier.  
Watch these two videos : 
- [What is Electricity?](https://www.youtube.com/watch?v=ag6ltdwqfms) 
- [Transistors Explained - How transistors work](https://www.youtube.com/watch?v=J4oO7PT_nzQ)

Types of Transistors: There are two main types of transistors: bipolar junction transistors (BJTs) and field-effect transistors (FETs). Each type operates differently and has distinct characteristics:

>BJTs: These transistors rely on the movement of charge carriers (electrons and holes) to control current flow. BJTs come in two types: NPN (negative-positive-negative) and PNP (positive-negative-positive).

>FETs: FETs use an electric field to control current. They come in various forms, including MOSFETs (Metal-Oxide-Semiconductor FETs) and JFETs (Junction Field-Effect Transistors).

MOSFETs are commonly used in microcontrollers and digital integrated circuits. They are preferred for switching applications due to their low power consumption, fast switching speeds, and high input impedance. They are mostly used in Embedded ICs

Both Field-Effect Transistors (FETs) and Bipolar Junction Transistors (BJTs) are used in various electronic applications, including microcontrollers (MCUs) and microprocessors. The choice between FETs and BJTs depends on the specific requirements and design considerations of the circuit. Here's a brief overview of their typical usage in MCUs:

Field-Effect Transistors (FETs):

    MOSFETs (Metal-Oxide-Semiconductor FETs): MOSFETs are commonly used in microcontrollers and digital integrated circuits. They are preferred for switching applications due to their low power consumption, fast switching speeds, and high input impedance. MOSFETs are often used in digital logic gates, memory cells, and output drivers for MCUs.

    CMOS Technology: Many modern microcontrollers are built using complementary metal-oxide-semiconductor (CMOS) technology, which relies on both n-type and p-type MOSFETs. CMOS technology provides low power consumption and high noise immunity, making it suitable for battery-powered and digital applications.

    Low Power Modes: MCUs often use MOSFETs in low-power modes to disconnect or minimize the power consumption of peripheral components when they are not in use, helping to extend battery life.

Bipolar Junction Transistors (BJTs):

    NPN and PNP BJTs: BJTs, both NPN and PNP types, are used in analog and mixed-signal microcontroller applications. They are commonly found in analog amplifiers, voltage regulators, analog-to-digital converters (ADCs), and other analog components.

    Amplification: BJTs are well-suited for amplification tasks in analog circuits. They can be used to amplify weak signals in analog sensors, communication interfaces, and audio circuits.

    Switching: While MOSFETs are preferred for digital switching due to their low power consumption, BJTs can still be used for low-frequency switching applications in MCUs.

In summary, both FETs (specifically MOSFETs) and BJTs have their roles in microcontroller and microprocessor applications:

    MOSFETs are commonly used in digital MCUs for logic, memory, and low-power switching.

    BJTs, particularly NPN and PNP types, find their place in analog and mixed-signal circuits within MCUs, where amplification and analog signal processing are required.

The choice between these transistor types depends on the specific functionality and requirements of the MCU's application. Modern microcontrollers often integrate a combination of both FETs and BJTs within their design to cater to diverse needs, making them versatile components for a wide range of applications.


For Comparison between BJT, MOSFET and IGBT, watch this [video](https://www.youtube.com/watch?v=VlMdSCI29A0)


## DRAM Vs SRAm
