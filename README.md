![Concert Header Image](https://raw.githubusercontent.com/puckowski/concert/master/Concert_Header.png)

<details>
<summary>
Click to expand snippet
</summary>
<p>

```cpp
import string;

const string WELCOME = "Hello, world!";

# Adler-32 is a checksum algorithm invented by Mark Adler in 1995.
function adler32 : string as message, int as messageLength -&gt; hash;
  const int DIVISOR = 65521;

  string char;
  int charValue;
  
  int s1 = 1;
  int s2 = 0;
  int n = 0;
  
  while n &lt; messageLength;
    call char_at : message, n -&gt; char;
    call to_int : char -&gt; charValue;
    
    s1 = (s1 + charValue) % DIVISOR;
    s2 = (s2 + s1) % DIVISOR;
    
    n += 1;
  end;
  
  s2 = (s2 &lt;&lt; 16) | s1;
return s2;

int welcomeLength;
call length : WELCOME -&gt; welcomeLength;

int hash;

call adler32 : WELCOME, welcomeLength -&gt; hash;
```
</p>
</details>

# Reference

## Basic concepts

[Types](types.md)

[Comments](commands.md)

[Identifiers](identifiers.md)

[Scope](scope.md)

## Keywords

[Keywords](keywords.md)

## Expressions

[Assignment](assignment.md)

[Operator precedence](operator_precedence.md)

[Comparison](comparison.md)

## Functions

[Functions](functions.md)

## Standard library

[Standard library](standard_library.md)
