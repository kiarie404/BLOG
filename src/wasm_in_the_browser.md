# wasm in the browser

I read the Kevin Hoffman's book on wasm in the browser. Cool. Insightful.     

I tried reading the official wasm specifications but the mathematic notations in the documents flew right past me. Sad, I know.  

In the end, I got the gist of things concerning a modules structure, raw WAT commands and some details on runtime requirements. I got to understand why they chose a stack machine too.  

I am yet to fully understand the security implementations of wasm itself and the corresponding runtime implementation.  

I am okay with using Rust + wasm. I don't like JS because I have no will to understand it... right now I can only love Rust. The rest is noise.  



Anyway, wasm in the browser is cool and all... but that is sincerely none of my business. I want to know wasm off-the-browser, where it makes real change. And eventually, move on to wasm in a no-std setup.  


Kevin Hoffman's book covers wasmi, a wasm runtime that can be embedded as a Rust crate. It can also run on no-std environments. It has WASI integration. But wasmi is an intepreter... I need a runtime that preferably has all implementations of Aot, JIT and interpretation.  

Then there is Wasmer... aagh, it is so sad that it is written in C, an unsafe language. We cannot touch something that hot, such a pity. I am a rust zealot.


<br><br>
**Bye bye browser... I hope I never see you again.** 
