
**Mutable**: it is a similar to constant but it is not needed to be known at the runtime
- can be different value at different run-times

**Const**: we need to know the value at the compile time
- at all run-time it is constant

***let***: for declaring variable.
***mut***: to make it mutable.
***const***: it is immutable constant.

```rust

let user_name = get_user_name(); // it can be received from user
const LOCALHOST = "127.0.0.1" ; // it is fixed
```


## Functions

```rust

fn add (a: i32, b:i32) -> i32 {
	a+b
}
```

here syntax is 
function name(parameters) -> return_type {
...
...
....body
..
.. 
last line is return value
}

## Macros
- Macro is the code that expands into additional code. like typedef in **C**
	- ! (exclamation mark) indicates the macro.
-  println!() -> print_line macro
## Enum
- it is a datatype where we set a different possiblities as value
- similar to bool but lot of options.
- the answer is called **variant***.
```rust

enum direction { // here direction is the custom dataype
	up,
	down, // -> variant
	left,
	right,
}

fn which_direction(go: Direction) {
	match go {
	Direction::up => println!("up"),
	Direction::down => println!("down"),
	Direction::left => println!("left"),
	Direction::right => println!("right"),
	}
}
fn main(){
	which_direction(Direction::color); // usage
}

```

## Struct
