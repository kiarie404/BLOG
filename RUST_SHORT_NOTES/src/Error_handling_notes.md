
These are my notes on error_handling written for quick reference, You will be better off reading about error_handling from the official Rust API documentation.   



- **Panic Runtime** - a set of instructions that are part of Rust's ABI implementation. They are a subset of the main Rust runime that deal specifically with handling panics. This set of instructions takes care of the following (I am guessing) 
  - Halting the current thread
  - Managing a part of the thread's runtime stack
  - Unwinding or discarding the thread's stack


- **Hook** - A hook is typically a set of instructions that gets immediately called when an event happens. When a panic() function gets called, a default hook gets called even before the panic runtime is invoked. The default hook prints a message to standard error and generates a backtrace if requested. In a no_std environment where there is no standard error, you will want to define your own hook.   

You can however submit your own custom hook using the set_hook() function even is a std setup.  

If you want to check the name of the current hook in use, use the 'take_hook' function. However, the take_hook function Unregisters the current panic hook and returns it, registering the default hook in its place. If the default hook is registered it will be returned, but remain registered.  

**panic! and panic_any** are macros that are used to initiate a panic. The payload is a datastructure that gets returned by the panic() function. Panic(&str) always takes a string payload. panic_any returns custom datastuctures apart from the string payload. 

**PanicInfo** - A struct providing information about a panic.   
PanicInfo structure is passed to a panic hook set by the set_hook function.  

**The Error Trait** 
The error trait can be defined on any type that already implements the Debug + Display trait.  
The functions that automatically get provided by the Error trait are 4, only one is relevant... the rest are deprecated or usable in nightly-only.

The relevant function is source(). 
You have hardcode your souorces across different modules.  
Check out this example :
```rust
use std::error::Error; // use the Error Trait
use std::fmt::{Display, Formatter, write}; // use the Display trait. For an item to be able to implement the Error trait, it must first implement both Debug & Display traits


#[derive(Debug)]
struct LowerError{  }

impl Display for LowerError{
    fn fmt(&self, f: &mut Formatter<'_>) -> Result<(), std::fmt::Error> { 
        write!(f, "I am LowerError")
    }
}

impl Error for LowerError{}


#[derive(Debug)]
struct HigherError {
    source : LowerError, // hardcoded source, I do not know if the Error::source function requires this field to be hardcoded
                         // I do not know if this field can take another name... I do not kow if I can leave it out and still call the source() and get a Some(Err) 
}

impl Display for HigherError {
    fn fmt (&self, f: &mut Formatter<'_>) -> Result<(), std::fmt::Error>{
        write(f, format_args!("I am HigherError"))
    }
}

impl Error for HigherError{
    fn source(&self) -> Option<&(dyn Error + 'static)> {
        Some(&self.source)
    }
}


fn get_higher_error() -> HigherError{
    HigherError { source: LowerError{} }
}



fn main(){

    let e = get_higher_error();

    println!("e = {}", e);
    println!("e source = {:?}", e.source());
    println!("e source error = {}", e.source().unwrap());
}
```



## Error Message Explanations.  

Trouble_shooting big prorgams is hard. Good error messages GO A LONG WAAAAYYYY. I mean...just look at the error messages that the Rust compiler provides... elegant as hell.    


This is why the compiler requires errors to have both the DISPLAY and DEBUG traits implemented. This is where you get to shine by elaborating your error messages using code... you are given a chance to even write an entire program to just display your error message.  

I prefer stating : 
    - The possible cause(s)
    - Possible solutions
    - Adding GUI demo if possible (just kidding ha ha ha)

You can add information such as 'which file position the error occured in' and 'which function was running?' 'which thread?'. But such info can be automatically derived from the panicInfo struct and inspecting the BACK-TRACE