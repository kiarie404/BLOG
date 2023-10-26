# Magic and Incantations

Kumbe there is more to OOP, Functional and procedural programming...

# Type State programming

Reference this page : https://docs.rust-embedded.org/book/static-guarantees/typestate-programming.html


   This shit is safe as hell. Organized piece of sh*.  
   - There is only one end state. 
   - All state operations can be clearly seen (in one place)
   - The end state cannot be affected by the process actions
   - Moves happen... not copies
   - This is like a state machine to produce a instance of something


   Something like this:
   ```rust
   pub mod foo_module {
    #[derive(Debug)]
    pub struct Foo {
        inner: u32,
    }

    pub struct FooBuilder {
        a: u32,
        b: u32,
    }

    impl FooBuilder {
        pub fn new(starter: u32) -> Self {
            Self {
                a: starter,
                b: starter,
            }
        }

        pub fn double_a(self) -> Self {
            Self {
                a: self.a * 2,
                b: self.b,
            }
        }

        pub fn into_foo(self) -> Foo {
            Foo {
                inner: self.a + self.b,
            }
        }
    }
}

fn main() {
    let x = foo_module::FooBuilder::new(10)
        .double_a()
        .into_foo();

    println!("{:#?}", x);
}
   ```
   
Now that we have a state diagram kind of representation, how do we ensure that the state flow is always valid?
1. We can use runtime checks using if-else and switch statements. But the checks are costy.
2. We can use struct interfaces and get compile-time checks only instead of relying on runtime checks