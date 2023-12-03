# wasmi runtime

These are quick notes that I wanted to remember, read the official wasmi docs for more info.

## The Engine 
The engine is a struct that abstracts the intepreter. In this case, the intepreter is the code that takes care of :
    - compiling the wat/wasm to machine code
    - Interacting with the underlying system to initiate execution of the machine code
    - Isolation of modules in execution
    - Communiccation between executing modules

The engine is taking care of a lot, that is why it provides a dedicated struct that contains configuration details. This struct is called **Config**.   
Config alters info such as : the number and depth of stacks used by the engine, whether the engine gets to support both f32 and f64... and so much more.    

You can however create an engine with default settings using the Engine::default function.  


## The wasmi::Module  
This is a struct that represents a wasm binary file that has been parsed and validated. You can inquire info about which engine was used in its validation, what its imports and exports are.  
```rust
// This function reads the wasm file that has been presented as a readable byte stream...
// It then passes on that byte-stream to the Engine, the engine validates that wasm file and either returns an error OR a Module
// The Module is not tied to the Engine that created it, The engine interacted with it immutably
pub fn new(engine: &Engine, stream: impl Read) -> Result<Self, Error>
```

## The wasmi::Caller  
This struct represents the context of the of the wasm scope where an external function has just been called. 
It is only useful as an argument when defining a host function that needs to use some objects from the wasm context.    
It is useless everywhere else...  
The only place it gets used is when you are defining a host function that (is defined with func_wrap) AND (needs to access some data from the wasm context). Other than that, you can define functions that do not need to use the wasm context.    



## The Store
The store is a datastructure that stores all the state that is accessible to the wasm program. It consists of the runtime representation of all instances of functions, tables, memories, and globals, element segments, and data segments that have been allocated during the life time of the abstract machine.   

Now, among the store's content... you can have data that was exported from the host. (it is an external Value). But there is a different kind of value... Host specific data. ds

