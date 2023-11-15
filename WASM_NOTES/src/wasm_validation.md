# Wasm validation

These are rough notes I took while reading the 'Validation' chapter in the official wasm specifications.  
If you want to understand the validation process, it is better to read the chapter itself because it is more structured.    

Validation is the process of making sure that the wasm module follows the language specifications. It does this by representing the wasm module as an abstract syntax tree and validating it. 

### What needs to be validated?
Here are some of the validation checkpoints 

#### 1. Type validation
- Are their unknown types?
- Are the limits set for things valid?  
- [not a check] Block types are converted to function types for easy processing. 

#### 2. Instruction validation
- Checks that the order of instructions make sense... 
- Checks that the insructions themselves adhere to their signatures. eg i32.add f64 i32 is messed up.

#### 3. Module validation
A module is entirely closed, that is, its components can only refer to definitions that appear in the module itself. That is if it does not import anything.  


During validation, the module is checked it contains valid components ONLY eg valid imports, exports, types, mems, data_segments, element_segments, tables, globals, locals, references, functions...   

