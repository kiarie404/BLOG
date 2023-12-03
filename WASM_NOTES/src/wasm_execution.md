# Wasm Execution

Wasm code gets executed under either of the 2 circumstances below:
    1. During instantiation (only if the module contains a start function)
    2. When the host invokes a function that had been exported by the wasm module.


Execution behavior is defined in terms of an abstract machine that models the **program state**.    
The program state is abstracted by 2 representations : A **stack** and a **store**.  


The **stack** records operand values and control constructs. (To me, this is like the RAM of the Machine)
The **store** contains global state. ie [undone] all values. I mean ALL values related to the wasm module. (To me this is like the a constantly updated Hard-disk, it contains all the values that are listed in the stack + other values that may get added to the stack in the future)  


For each instruction contained in the wasm code, there is a rule that specifies the effect of its execution on the program state. The execution rules assume that the stack is implicit; this is because it is assumed that the type system can calculate the max depth needed at compile time.  

**The store** represents all global state that can be manipulated by WebAssembly programs. It consists of the runtime representation of all instances of functions, tables, memories, and globals, element segments, and data segments that have been allocated during the life time of the abstract machine.

Here is a struct that demonstrates a store :
```rust
store ::=
{ 
    funcs : vec<func_instance> ,
    tables : vec<table_instance> ,
    mems : vec<mem_instance> ,
    globals : vec<global_instance> ,
    elems : vec<elem_instance> ,
    datas : vec<data_instance>
}
```

A **module instance** is the runtime representation of a module. It is created by instantiating a module, and collects
runtime representations of all entities that are imported, defined, or exported by the module.  

Then from the module instance we have component instances of things like : memory instance, global instance, function instance... you get the vibe.  

You can read of the implementation specs in the docs... ignore the formal notations if you wanna, it won't affect your conceptual understanding of the docs.  


