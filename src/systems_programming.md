# Systems Programming

Our first step is to get good at computation spells.    

Yea, we need to be good programmers. We need to master our swords : Rust, Wasm and Riscv.   
We need to be awesome developers : Our aim is to understand different programming philosophies and embue them into our DNA and our thinking.    

You could say this is all about creating good abstractions and finding the best way to manipulate those abstractions.  
Along this journey... we will learn :   
 1. How to be good at functional programming too... time to stop using OOP everywhere. There is more to life now, we gotta learn what we can...open our minds more.
 2. Learn programming patterns by heart, especially patterns that are effective in concurrent environments. For example, implementing Singletons that are thread safe, developing corrupt-free routing...
 3. Good old practices : Testing, Error-handling, Documentation, Performance optimization.

We will create an Embedded OS... let's call it HOBO OS. Because we don't care if we go homeless for the sake of magic.  

Hobo OS will be an OS that :
   1. Runs wasm modules in Ring 0 for the sake of performance. Running things in Ring 0 is scary... but the kernel itself is a carefully written wasm runtime that enforces isolation well. Plus it is capability-based system.
   2. Exposes its kernel interface as WASI prototypes. We hope WASI APIs will prevail in the future. POSIX is old and limited. Using WASI encourages portability across different domains. This is because WASI provides APIs for different domains on top of OS level APIs... for example, WASI for Neural networks, WASI for cloud... This will make the OS to be easily extensible. Using WASI has disadvantages and advantages, we will open that can of worms in later chapters... for now... "trust me bro".
   3. Targets the Riscv ISA. We do not tolerate other ISAs. 
   4. Can receive over the Air updates.
   5. Can use AoT, JIT and Intepreter when required.  
   6. Other features will be added in the [full documentation of the Hobo OS](undone)


In the future, Hobo OS will hopefully be ported to Tock. I highly respect the Tock OS project. Go check Tock out. Those guys have balls. Big BIG balls.  

Another integration would be the concepts of Sel4 and Theseus.  
From Sel4, we borrow their concept of mathematically testing the kernel.    
From Theseus, we borrow their compiler-based isolation techniques.  




