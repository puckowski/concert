# Keyword function

## Description

Declare a function.

## Example

```cpp
function helloWorldWithName : using NAME;
  println "Hello, ", NAME, "!";
return;

const string NAME = "John Doe";

call helloWorldWithName : NAME;
```
