# cargo_component_model

Read the docs at this [crates.io page](https://crates.io/crates/cargo-component)

The cargo component helps you treat wasm modules like normal crates. It does this by enabling the following functions :

1. You can casually declare a wasm modules and components as a crate_dependency in your cargo.toml file 
2. Reference the wasm dependency like you would an external crate (via bindings::<name_of_wasm_dependency>::...) in your source code
3. Give you a tool to build your own components using the "cargo component build" command.  
4. Give you access to other commands that assist in manipulating components... go read the docs. 

- You need to run the "cargo component build" command before running the "cargo build" command. This is because the 'cargo build' command builds the entire repo while the 'cargo component build' command builds the dependencies that are used within the repo. So it makes sense to first build the dependencies before building the (dependent) entire repo.    

**What are bindings?**   
Bindings is a collection of glue code that helps in the interaction between the host programming language and a wit-defined component.  
Wit-bindgen is one of the libraries that does this.  
You could say it defines the translation from wit to another language(eg Rust).  
A library absraction above the wit interface.  

So that is why we reference it in our crate as bindings::<name_of_wasm_dependency>::<some_public_item_from_wasm_component>   
The 'cargo component build' stores all the bindings generated from each wasm_coponent dependency into the ./target/bindings folder.  




In the future, cargo will hopefully support wasm_components in a built-in fashion. For now we have to use 3rd party crates like cargo-component.  
I also hope that warg will work seamlessly with cargo and other package managers.   

What bugs me now?   
- I cant have wits defined under multiple package names. But this is no urgent matter
- I don't know how to organize my repo to be more ergonimic... more future proof.
- What do you mean I can't use underscores when naming things?

**Reactor components vs Command components**    
A reactor component is like a lib crate, it contains no 'run' function. In this case it would be a crate that does not have main.   
A command coponent is a crate that has a 'run' function, in this case, it would be a component made from a crate that had a main function.  

