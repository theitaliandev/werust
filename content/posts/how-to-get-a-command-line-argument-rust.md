---
title: "How to Get a Command Line Argument in Rust?"
date: 2023-01-16T10:12:21Z
description: "Learn how to easily access command line arguments in Rust with code examples and explanations. Quickly get specific arguments using the nth() and get() functions"
ShowToc: true
---

Getting *command line arguments in Rust* is relatively straightforward. The ***`std::env::args()`*** method returns an iterator over the arguments passed to the program. Here is an example of how to access the command line arguments in a Rust program:

```
use std::env;

fn main() {
    let args: Vec<String> = env::args().collect();

    println!("Arguments passed to the program:");
    for (index, arg) in args.iter().enumerate() {
        println!("{}: {}", index, arg);
    }
}
```

In this example, we first use the `collect()` method to convert the iterator returned by `std::env::args()` into a vector of strings. This allows us to easily iterate over the arguments using a for loop.

The first element in the vector `(args[0])` will always be the name of the program, so if you want to access the actual arguments passed to the program, you will need to start at `args[1]`.

## Using the nth() function

You can also use the ***`nth()`*** function of iterator to get the specific argument of command line

```
use std::env;

fn main() {
    let first_arg = env::args().nth(1);

    match first_arg {
        Some(arg) => println!("The first argument passed to the program is: {}", arg),
        None => println!("No arguments were passed to the program"),
    }
}
```

## Using the get() function

You can also use the ***`get()`*** function of vector to get the specific argument of command line

```
use std::env;

fn main() {
    let args: Vec<String> = env::args().collect();
    let second_arg = args.get(2);

    match second_arg {
        Some(arg) => println!("The second argument passed to the program is: {}", arg),
        None => println!("No second argument was passed to the program"),
    }
}
```

In this example, we first use the `collect()` method to convert the iterator returned by `std::env::args()` into a vector of strings. Then we use the `get()` function to get the specific argument of command line.