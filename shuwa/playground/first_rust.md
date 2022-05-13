# Libraries
- Core Library
This includes stand-alone functionalities of Rust, which are not dependent on platforms
or other system libraries. Fundamental types such as numeric types, `str`, tuple, and 
array.

- Standard Library
This is implemented as `std` and includes useful types such as `Vec`, `Options`, `Result`.

# Basic syntax
## Types

#### Numbers
```
(i)nteger/(u)nsigned/(float)   
| --- memory bits: 8,16,32,64,128,size 
| | 
i38
```
- *float* only has `f32` and `f64`
- `size` has system architecture-dependent size of data. It will be 32 bits long on 32-bit
architecture systems, and 64 bits long on 64-bit architecture systems. 
- `usize` is mainly used to access elements of arrays/vectors or to express sizes

#### Strings
##### str
`str` is the only string type defined in the core library.
This is called "string slice" as it only points to beginning and terminal addresses of 
data consisting of characters stored memory. Because of such a structure, 
it can only handle fixed size of data, and it is impossible to change the content of 
the string on memory.


A use case of `str` type will be where you have a pre-defined string in an application and
refer it as `&str`. [^1]


##### String
`String` is a string data type defined in standard library, and its stored data or 
length are mutable. `String` is commonly preferred over `str` type especially when
there will be string manipulations.


##### Notes
- When converting a `String` type item into `&str` item, the programme will copy the data 
length and pass the pointer, meaning that it will not consume any further memory space.
- However, the programme will allocate designated memory space when converting `str` item into `String` item.

```rust
let tests: String = String::from("Hello, world!");
let tests2: &str = &tests;  // String --> &str
let test3: String = &tests2;  // &str --> String
```


[^1]: putting `&``before type name indicates that the reference must be fetched in that 
type. 
