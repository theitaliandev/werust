---
title: "What does &'static str Mean? - Rust Static Lifetime"
date: 2023-01-16T22:01:58Z
description: "Learn about &'static str in Rust: a reference to a string with a static lifetime. Includes examples and differences with &str."
ShowToc: true
---

`&'static str` in Rust is a reference to a string that has a **static lifetime**. A lifetime in Rust is a way to ensure that a reference to a value is valid for a certain period of time. The static lifetime, denoted by the keyword static, means that **the reference will be valid for the entire duration of the program**.

Here's an example of using a `&'static str`:

```
static HELLO_WORLD: &'static str = "Hello, world!";

fn main() {
    println!("{}", HELLO_WORLD);
}
```

In this example, the variable HELLO_WORLD is a static reference to the string "Hello, world!". Because it has the static lifetime, it can be used anywhere in the program without the need for an explicit lifetime annotation.

It's important to note that `&'static str` is different from `&str`, which is a reference to a string with an unknown lifetime. For example, this code will not work:

```
fn main() {
    let s = "Hello, world!";
    static HELLO_WORLD: &str = s;
    println!("{}", HELLO_WORLD);
}
```

This is because the lifetime of the reference in `HELLO_WORLD` is not known, and the compiler will throw an error. To fix this, you can either use `&'static str` or explicitly annotate the lifetime of the reference:

```
fn main() {
    let s = "Hello, world!";
    static HELLO_WORLD: &'static str = &s;
    println!("{}", HELLO_WORLD);
}
```

or

```
fn main() {
    let s = "Hello, world!";
    static HELLO_WORLD: &'a str = s;
    println!("{}", HELLO_WORLD);
}
```

For more information on lifetimes and references in Rust, you can refer to the Rust documentation on [static lifetime syntax](https://doc.rust-lang.org/book/ch10-03-lifetime-syntax.html?highlight=static#the-static-lifetime).