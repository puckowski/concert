[Home](https://puckowski.github.io/concert/)

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

Example "simpleRet" function declaration:

```cpp
function simpleRet;
```

Example "simpleRet" function. Function returns the value 5.

```cpp
function simpleRet;
return 5;
```

Example "formattedPrint" function declaration. Function accepts a string type parameter. The string parameter is pass by value. The string parameter is assigned the identifer "msg" for the scope of the function.

```cpp
function formattedPrint : with string as msg;
```

Example "formattedPrint" function:

```cpp
function formattedPrint : with string as msg;
    println "Hello, " msg;
return;
```

Example "incrementVar" function declaration. Function accepts an int type parameter. The int parameter is pass by reference. The int parameter is assigned the identifier "toInc" for the scope of the function. 

```cpp
function incrementVar : using toInc;
```

Example "incrementVar" function:

```cpp
function incrementVar : using toInc;
    toInc += 1;
return;
```

Example "sum" function declaration. Function accepts two int type parameters. The first int parameter is passed by reference. The second int parameter is passed by value and assigned the identifier "toAdd" for the scope of the function.

```cpp
function sum : using count, with int as toAdd;
```

Example "sum" function. The function returns the value count.

```cpp
function sum : using count, with int as toAdd;
    count += toAdd;
return count;
```

Example "sum" function declaration using pass by reference shorthand "&". This "sum" function is equivalent to the example "sum" function above.

```cpp
function sum : &count, with int as toAdd;
    count += toAdd;
return count;
```
