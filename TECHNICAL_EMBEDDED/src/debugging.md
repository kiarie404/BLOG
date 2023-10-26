# Debugging

References : 
- long video (debugging series)

Debugging is a VERY IMPORTANT process. It is the process of finding bugs in code by inspecting the program's flow (cause and effect). Almost like real-time observation of how cause and effect happens during execution.  
You can do this by running the program in a step-wise manner OR EVEN inspecting the stepwise-logs after the program has executed. The point being that you are checking all the cause-effects that happened while the program executed. 

Embedded debugging is tricky. Here is a short book on debugging for embedded systems while working with Rust --> [Debugonomicon](https://docs.rust-embedded.org/debugonomicon/)


Shortnotes from the above mentioned book ([Debugonomicon](https://docs.rust-embedded.org/debugonomicon/)):  

### Debugging Protocol
Protocol between the Debugger and target MCU.   

A debug protocol, in the context of software development and embedded systems, is a set of rules and conventions that define how a debugger (debugging tool or software) communicates with the target system being debugged. It establishes a standardized way for the debugger to interact with the target system's hardware or software to perform various debugging tasks, such as setting breakpoints, reading memory contents, controlling program execution, and retrieving debugging information.

Key aspects of a debug protocol include:

    Communication Protocol: It specifies the communication medium and the data format used for exchanging information between the debugger and the target system. Common communication mediums include serial ports, USB, Ethernet, JTAG (Joint Test Action Group), SWD (Serial Wire Debug), or custom interfaces.

    Commands and Responses: The protocol defines a set of commands that the debugger can send to the target system and the corresponding responses that the target system provides. These commands typically cover actions like starting or stopping program execution, reading and writing memory, setting breakpoints, stepping through code, and querying system status.

    Debugging Information: The protocol may include provisions for retrieving debugging information from the target system. This information can include register values, memory contents, program symbols, and stack traces, which are valuable for diagnosing issues during debugging.


### A debug adapter
This is a piece of hardware that stands between the host system and target system. It acts as a intermediary; 