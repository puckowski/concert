# Operator precedence
  
| Precedence | Operator | Description                 |
|:-----------|:---------|:----------------------------|
|1           |[]        |Subscript                    |
|2           |<<        |Bitwise left shift           |
|2           |>>        |Bitwise right shift          |
|3           |*         |Multiplication               |
|3           |/         |Division                     |
|3           |%         |Remainder                    |
|4           |+         |Addition                     |
|4           |-         |Subtraction                  |
|5           |\|         |Bitwise OR                   |
|5           |&         |Bitwise AND                  |
|5           |^         |Bitwise XOR                  |

## Subscript example

```cpp
int array 10 = 0;
int currentIndex = 0;
int currentValue = 5;

# Value of array at index 0 will equal 5 after assignment.
array[0] = array[currentIndex] + currentValue;
```
