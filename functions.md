# Functions

Example "hello" function declaration:

```cpp
function hello;
```

Example "hello" function:

```cp
function hello;
  print "Hello";
return;
```

Example "simpleRet" function declaration. Function stores return value in variable with identifier "x".

```cpp
function simpleRet -> x;
```

Example "simpleRet" function:

```cpp
function simpleRet -> x;
return 5;
```

Example "formattedPrint" function declaration. Function accepts a string type parameter. The string paramater is a copy of the original data. The string parameter is assigned the identifer "msg" for the scope of the function.

```cpp
function formattedPrint : with string as msg;
```

Example "formattedPrint" function:

```cpp
function formattedPrint : with string as msg;
  println "Hello, " msg;
return;
```

Example "incrementVar" function declaration. Function accepts an int type parameter, with identifier "toInc", by reference. 

```cpp
function incrementVar : using toInc;
```

Example "incrementVar" function:

```cpp
function incrementVar : using toInc;
  toInc += 1;
return;
```

Example "sum" function declaration. Function accepts two int type paramaters. The first int parameter is passed by reference. The second int parameter is passed by value and assigned the name "toAdd" for the scope of the function. The function returns a value, which is stored in the variable "result".

```cpp
function sum : using count, with int as toAdd -> result;
```

Example "sum" function:

```cpp
function sum : using count, with int as toAdd -> result;
  count += toAdd;
return count;
```

Example "sum" function declaration using pass by reference shorthand "&". This "sum" function is equivalent to the example "sum" function above.

```cpp
function sum : &count, with int as toAdd -> result;
  count += toAdd;
return count;
```
