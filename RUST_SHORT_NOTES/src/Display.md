These are just short notes, you are better off reading from the official Rust API documentation.    
Especially the std::fmt module OR core::fmt



("this is a {} format string {}", these, are, format, arguments );

**core::fmt::Arguments** is a struct that represents a safely precompiled version of a format string and its arguments. This cannot be generated at runtime because it cannot safely be done, so no constructors are given and the fields are private to prevent modification.  

The **format_args! macro** produces an Argument after consuming (format_string and format_arguments)    

The **core::fmt::Formatter** is a struct that contains configuration on how to format text. It acts as a builder pattern for the string that will get eventually pushed to the underlying buffer.  

The Formatter is not a global or singleton formatter that applies to all values universally in your program; Each time you call the fmt function within a Debug or Display implementation, you get a new instance of Formatter.

Each Formatter is attached to an anonymous buffer. A buffer is something that implements the Write Trait that has been discussed below. The Formatter has the Write trait defined, making it a buffer by its own right... so the earlier sentence about it haveing a buffer attached to it was wrong --- IT IS THE BUFFER ITSELF



**Trait Write** - This is the trait that a buffer needs to implement. This trait requires you to define how a string fits into your buffer structure. There are 2 kinds of write traits; **core::fmt::Write** and **Trait core::io::Write**. If you want to make that buffer flushable use the io::write, else use the fmt::write trait.

**The write function** - the write function takes in a Buffer + a precompiled string (Argument). It then puts that precompiled string into the Buffer as specified by the Buffer's Write Trait implementation.  

**The write macro** - the write macro takes in a Buffer + format string + arguments. It then dumps that format_string and arguments into the buffer as specified by the Write Trait functions.
  
**The writeln macro** - self explanatory


The Display implementation :
```rust
impl fmt::Display for SuperError {
    // the Formatter builder struct implements the Write trait
    fn fmt(&self, f: &mut fmt::Formatter<'_>) -> fmt::Result {
        write!(f, "SuperError is here!")
    }
}   
```