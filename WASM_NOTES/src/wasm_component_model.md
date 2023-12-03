# Wasm Component Model

The docs for the wasm component model are well explained. It would be a diservice to re-explain them  in a less clear manner.   
You can find its documentation [here](https://component-model.bytecodealliance.org/)    

So here are short notes...

A wasm component != A wasm core module != A wasm core module embedded with a wit file as a custom section.  
This is important because it affects the way runtimes and compilers treat your file. For example, the core wasm parser cannot parse a wasm component because the wat formats are different.  

Not all languages have been able to tweak their compilers to target wasm. And among the languages that are targeting wasm, there are some that have more support than others.   

By support I mean :  
- The version of wasm they support by default.  
- The post-mvp features taken into account by the language compiler
- The tooling that deals with wasm and wat files


The features that I value are :
1. WASI 
2. The component model
3. Capability based security monitoring
4. No-std support

I am also interested in rust-based toolchains over other equally-worthy toolchains. I am biased.    
[wasm-tools](https://github.com/bytecodealliance/wasm-tools) are great. They are component-friendly. Using tools like online wat/wasm parsers result in parsing errors because they have not taken the component model into account. They can handle embedded wasm modules, but they cannot handle Components.wasm (james, explain this clearly please)

wasm-tools vs wabt's wasm-wat convertors. 
1. The *embedded* wat files by wasm-tools do not show custom sections as commented code. The one from wabt does. 
2. The  

**Questions**
1. Are components portable across all runtimes? Even the runtimes that are made to only handle core wasm modules?  
2. 