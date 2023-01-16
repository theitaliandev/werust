---
title: "How to get a substring of a String in Rust?"
date: 	2023-01-16T18:28:27Z
description: "Learn how to get a substring of a String in Rust with code examples for substring(), slice(), and chars().collect() methods."
ShowToc: true
---

In Rust, you can use the `substring()` method or the `slice()` method to get a substring of a String.

## substring() method

The `substring()` method takes two arguments: the starting index and the ending index of the substring. The substring includes the characters at the starting index and all the characters up to, but not including, the ending index. For example:

```
let original_string = String::from("Hello, World!");
let substring = original_string.substring(7, 12);
println!("{}", substring); // Output: "World"
```

## slice() method

The `slice()` method takes two arguments: the starting index and the ending index of the substring. The substring includes the characters at the starting index and all the characters up to, but not including, the ending index. The key difference between the `substring()` and `slice()` is that the `slice()` method returns a slice rather than a new String. For example:

```
let original_string = String::from("Hello, World!");
let substring = &original_string[7..12];
println!("{}", substring); // Output: "World"
```

## chars() method

Alternatively, you can use the `chars()` method to iterate over the characters of a String and collect a subset of them into a new String using the `collect()` method. Here's an example:

```
let original_string = String::from("Hello, World!");
let substring: String = original_string.chars().skip(7).take(5).collect();
println!("{}", substring); // Output: "World"
```

In this example, the `skip(7)` method skips the first 7 characters of the String, and the `take(5)` method takes the next 5 characters, which are the characters of the substring. The `collect()` method then collects these characters into a new String.

All of these examples will give you the substring "World" from the original String "Hello, World!".

It is important to note that **the substring produced will be valid as long as the original String is alive and not modified.** If you need the substring to live longer than the original string, you will need to create a new string and copy the substring into it.