# Tools

## Generic

- Rustup will help you install, modify and inquire toolchains. Master it.
- Master Cargo

- Cargo Binutils will help you integrate LLVM tools with cargo. nm, LLD(rust-lld), objdump, size, readobj. 
- Just mess aroud with LLVM and GNU tools. You need them BAD.  

- Cargo generate will help you pass templates to your team members


## Specific

- gdb-multiarch. (when actually debugging, refer to the specific gdb subset command eg arm-none-eabi-gdb)
- openocd (software that sits in between the GDB(in hosted environment) and Microcontroller-Debugger(in embedded environment))
- qemu-system-arm (this is not just Qemu)