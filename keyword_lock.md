# Keyword lock

## Description

Lock a declared mutex.

## Example

```cpp
mutex m;

lock m;
  println "Critical section.";
unlock m;
# Left critical section
```
