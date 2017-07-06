[Home](https://puckowski.github.io/concert/) <span>&emsp;</span> [Standard library](https://puckowski.github.io/concert/standard_library.html)

# Input output library

Provides standard input and output functions.

## Import

The following statement may be used to import the input output library:

```cpp
import io;
```

## Functions

| Name              | Description                                                       |
|:------------------|:------------------------------------------------------------------|
| open_file         | Open an existing file for input and output. Optional binary flag. |
| close_file        | Close an open file                                                |
| write_string      | Write a string to a file                                          |
| get_line          | Get a line from a file                                            |
| is_open           | Check if a file is open                                           |
| is_end            | Check if read file contents to end                                |
| is_file_exist     | Check if file exists                                              |
| create_file       | Create a new file                                                 |
| get_file_size     | Return file size                                                  |
| seek_file_pointer | Seek binary file pointer to byte position                         |
| read_byte         | Read a byte from a file                                           |
| write_byte        | Write a byte to a file                                            |
| remove_file       | Remove a file                                                     |
| rename_file       | Rename a file                                                     |
| tell_file_pointer | Return the byte position of the binary file pointer               |

## Examples

### open_file

```
call open_file : "create_file_test.txt";
```

### close_file

```
call close_file : "create_file_test.txt";
```

### write_string

```
call open_file : "create_file_test.txt";
call write_string : "create_file_test.txt", "Hello, world!";
call close_file : "create_file_test.txt";
```

### get_line

```
call open_file : "create_file_test.txt";
string getLineResult;
call get_line : "create_file_test.txt" -> getLineResult;
call close_file : "create_file_test.txt";
```

### is_open

```
int isFileOpen;
call is_open : "create_file_test.txt" -> isFileOpen;
```

### is_end

```
call open_file : "create_file_test.txt";
isFileAtEnd = 0;
call is_end : "create_file_test.txt" -> isFileAtEnd;
call close_file : "create_file_test.txt";
```

### is_file_exist

```
int musicManagerExist;
call is_file_exist : "musicmanagerinstaller.exe" -> musicManagerExist;
```

### create_file

```
call create_file : "create_file_test.txt";
```

### get_file_size

```
int musicManagerSize;
call get_file_size : "musicmanagerinstaller.exe" -> musicManagerSize;
```

### seek_file_pointer

```
const int OPEN_AS_BINARY = 1;
call open_file : "create_file_test.txt", OPEN_AS_BINARY;
int filePointer = 1;
call seek_file_pointer : "create_file_test.txt", filePointer;
call close_file : "create_file_test.txt";
```

### read_byte

```
const int OPEN_AS_BINARY = 1;
call open_file : "create_file_test.txt", OPEN_AS_BINARY;
int byte;
call read_byte : "create_file_test.txt" -> byte;
call close_file : "create_file_test.txt";
```

### write_byte

```
const int OPEN_AS_BINARY = 1;
call open_file : "create_file_test.txt", OPEN_AS_BINARY;
call write_byte : "create_file_test.txt", 63;
call close_file : "create_file_test.txt";
```

### remove_file

```
call remove_file : "create_file_test.txt";
```

### rename_file

```
call rename_file : "create_file_test.txt", "create_file_test_2.txt";
```

### tell_file_pointer

```
const int OPEN_AS_BINARY = 1;
call open_file : "create_file_test.txt", OPEN_AS_BINARY;
int filePointer = 0;
call tell_file_pointer : "create_file_test.txt" -> filePointer;
call close_file : "create_file_test.txt";
```
