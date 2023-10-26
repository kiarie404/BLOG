# no std and Runtimes

Turns out every language has a runtime. Who knew? Even C and Rust.  
The Runtime takes care of things like panic handling, stack protection, order of functions called before main.  

Lib core is part of Std lib.  
In Rust, the runtime is part of the std lib.  

The compiler can work without the lib core and stdlib. As long as you satisfy all the language items required by the compiler. If you check the lib-core code, you will see things labelled as language items. This is how the compiler knows the position of code that satisfies the behavior of Rust itself

I have not understood the concept of [lang items](https://manishearth.github.io/blog/2017/01/11/rust-tidbits-what-is-a-lang-item/?ref=ductile.systems). Read about them [here](https://manishearth.github.io/blog/2017/01/11/rust-tidbits-what-is-a-lang-item/?ref=ductile.systems)

I have not understood the Rust Runtime. I do not how they are intertwined with the C runtime. I really don't know. [But this page has clues](https://ductile.systems/rusts-runtime/)



Anyway, when we stop depending on the std library...
1. you have to include your own init code before main()
2. you have to implement your own stack overflow protection mechanism
3. You have to implement your own std fuctions.
4. You may create your heap byte-allocator and iterface it with the Rust Alloc crate. That way you get to perform built-in Rust heap operations like Box Operations and vectors (use collections crate)
