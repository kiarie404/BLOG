# Wasm Specs

Again... these are short notes. A LOT has been left out. Read the latest official Docs to get full, structred information.  

**Values**  
The supported types are :
    - i32 (get used also as Boolean & memory addresses.)
    - i64
    - f32
    - f64
    - A 128 bit type that acts as an Array/vector. You can insert the above base types into this 128-bit vector.
    - Opaque references : opaque references refer to a type of data that represents pointers to different kinds of entities, but unlike other types, their size or representation is not observable.  

**opaque references**   
These are references whose size or structure are hidden for security purposes. Meaning their bit patterns cannot be observed. In this case, the references are hidden from the wasm program itself. However, the references might be viewable to the runtime since it is the one that enforces the concealment. For example, you might need to hide references pointing to data from the Host.  

The opposite of Opaque values is **transparent values**. Meaning that the bit patterns of the values are observable because they are not hidden.  

**A table** 
A table is a collection of indices that point to Opaque values. For now, the opaque values can be either Function references or value references. The runtime can therefore put an opaque reference to a host value.    
We need a table to help us implement dynamic calls and dynamic data-referencing in programs.  
Without it, we would have had to implement dynamicism through other methods such as an exhaustive compile-time monorphization. which would have resulted in bigger code size.  

**Element Segments**    
Items stored in the table are called elements. The indices of the table are called element indices.   
When a wasm module is loaded by the runtime, All tables are initially empty. So it is up to the runtime to start filling the table accordingly.  
So the runtime checks if there is an "element segment" defined. An element segment is a place in the wasm code where 
    - some elements have bee defined and are just waiting to be copied to the table
    - there are some instructions on how to load those elements or pre-create new ones  

An element segment is actually a vector of elements. The elements within can be in one of the following modes :
 1. Passive - it means you can copy them into the Table using the table.init instruction
 2. Active - It means that that segment gets automatically added to the table during module initialization
 3. Declarative - I did not understand this [undone]



**Linear Memory**   
A linear memory is a contiguous, mutable array of raw bytes. Such a memory is created with an initial size but can be grown dynamically. A program can load and store values from/to a linear memory at any byte address (including unaligned). Integer loads and stores can specify a storage size which is smaller than the size of the respective value type. A trap occurs if an access is not within the bounds of the current memory size.    
  


**References in wasm**  
A reference points to either an external object or a function.  
So we have the following grammar notation : [reftype ::= funcref | externref]   
All references in this case are opaque  

**Limits to memory or tables**  
Limits classify the size range of resizeable storage associated with memory types and table types.  
If no maximum is given, the respective storage can grow to any size.    
Being that memory addresses are represented by 32bit integers, memory size cannot be larger than (2^32)bytes where 1 page = 64KB


**Data segments**  
The linear memory of the wasm module is usually empty before instantiation. So during instantiation, the runtime goes to look for a data segment(s) to see which variables it can load into the linear memory.  
A data segment is a vector that contains variables that need to be loaded into the linear memory.  
Variables that need to be immediately loaded at instantiation are labelled as : **Active**  
Variables that can be loaded later through instructions such as mem.init are labelled as **passive**  

**Context** 
Context is a collection of all the components in a certain scope. Here is a struct that abstracts this concept :
Context ::=
{   
    types //
    funcs
    tables
    mems
    globals
    elems
    datas
    locals
    labels
    return
    refs
    functype * ,
    functype * ,
    tabletype * ,
    memtype * ,
    globaltype * ,
    reftype * ,
    ok * ,
    valtype * ,
    resulttype * ,
    resulttype ? ,
    funcidx * 
}


**Miscellaneous**   
The type system ensures that the stack height, and thus any referenced register, is always known
statically. So the operand stack is implicit.  

When an unrecoverable error occurs in the wasm code, a trap is thrown and the wasm code stops executing. the trap gets passed on to the host environment.   

Functions can call each other, including recursively, resulting in an implicit call stack that cannot be accessed directly.  

You can export something with one or more names... that's cool  
If you define a start function, it will act as main(). This is where execution will begin.

Vector instructions (also known as SIMD instructions, single instruction multiple data) provide basic operations
over values of vector type for the sake of performance.  

The unreachable instruction causes an unconditional trap.   

Each export is labeled by a unique name. Exportable definitions are functions, tables, memories, and globals,
which are referenced through a respective descriptor.  



