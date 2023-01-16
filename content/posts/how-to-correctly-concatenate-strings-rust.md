---
title: "How to correctly concat Strings in Rust?"
date: 	2023-01-16T16:19:09Z
description: "Learn how to correctly concatenate strings in Rust with code examples. Learn different methods like +, format!, push_str(), +=, join(), and concat() to concatenate strings in Rust."
ShowToc: true
---

## Using the + operator

Rust provides several ways to concatenate strings. The most common method is to use the `+` operator to concatenate two strings. Here is an example:

```
let s1 = "Hello";
let s2 = " World";
let s3 = s1 + s2;
println!("{}", s3); // Output: "Hello World"
```

## Using the format! macro

Another way to concatenate strings is to use the `format!` macro. This method is useful when you want to concatenate multiple strings and include variables in the final string. Here is an example:

```
let s1 = "Hello";
let s2 = " World";
let s3 = format!("{} {}", s1, s2);
println!("{}", s3); // Output: "Hello World"
```

## Using the push_str() method

You can also use the `push_str()` method to append one string to another. This method modifies the first string, unlike the previous two methods which create a new string. Here is an example:

```
let mut s1 = String::from("Hello");
let s2 = " World";
s1.push_str(s2);
println!("{}", s1); // Output: "Hello World"
```

## Using the += operator

Another way to concatenate string is to use `+=` operator

```
let mut s1 = String::from("Hello");
let s2 = " World";
s1 += s2;
println!("{}", s1); // Output: "Hello World"
```

## Using the join() method

You can also use the `join()` method on a vector of strings to concatenate them with a separator. Here is an example:

```
let v = vec!["Hello", "World"];
let s = v.join(" ");
println!("{}", s); // Output: "Hello World"
```

## Using the concat() method

It's also worth noting that Rust has a `concat()` method on the str type that allows you to concatenate multiple strings. However, **this method requires all input strings to be of the same lifetime.**

```
let s1 = "Hello";
let s2 = " World";
let s3 = "Rust";
let s4 = [s1, s2, s3].concat();
println!("{}", s4); // Output: "Hello World Rust"
```

You can use any of the above method as per your requirement.