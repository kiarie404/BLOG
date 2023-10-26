# Micro_controller vs General Purpose Computer

A microcontroller in this case can also be called a SoC. System on chip.    
An SoC is a single PCB with all required components attached.   

A general Computer might also have all components attached to the same PCB, but chances are that it will have many PCBs.    

## Differences

| SoC                                                                           | GPC                                                    |
|-------------------------------------------------------------------------------|--------------------------------------------------------|
| has one PCB                                                                   | Has at least one PCB                                   |
| Has only the components that are needed by a certain application              | Has Components that might be needed by any application |
| The Processor might lack certai functionalities, eg Floating point operations | Processor has many functionalities                     |
| Cheap  (few components)                                                       | Less Cheap (many components included)                  |
| Uses less power because: less components                                      | Uses more power                                        |
|                                                                               |                                                        |

## When to use SoC
1. When the operation is critical. eg in a medical device or a braking system. This is because A general purpose computer and OS usually has many software components which share the computer's processing resources. This makes it harder to guarantee execution of a program within tight time constraints.
2. Cost. A microcontroller is much cheaper than a general purpose computer. Not only is the microcontroller cheaper; it also requires many fewer external electrical components to operate. This makes Printed Circuit Boards (PCB) smaller and cheaper to design and manufacture.
3. Power consumption. Most microcontrollers consume a fraction of the power of a full blown processor. For applications which run on batteries, that makes a huge difference.
4. Reliability ; reduced components == reduced complexity == easy to maintain and trouble shoot

## When to avoid SoC
1. When running complicated algorithms. The processor of the SoC may lack complicated features. (eg floating point operations), such that if you include these operations, the CPU will have to do many cycles that end up consiming power.
2. When you expect to run general programs. Use an soC when the program that you want to run is Specialized
3. 


