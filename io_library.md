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
