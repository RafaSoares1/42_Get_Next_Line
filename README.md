# Get_Next_Line
Get Next Line is a project at 42.  It is a function that reads a file and allows you to read a line ending with a newline character from a file descriptor. When you call the function again on the same file, it grabs the next line. This project deals with memory allocation and when to free and allocate memory to prevent leaks.

## What to know?

**Static variable**

- Remains while the program is running. .<br />
- Is allocated memory in data segment.<br />

⚠️ Difference between global and static variable is that static variable cannot be accessed from other files..<br />

### Why using static variable
We need to call get_next_line until EOF, so we need a static variable to hold a line read with the amount of BUFFER_SIZE until the program ends.

### File descriptor
- An abstract indicator used to access a file in Unix and related computer operating systems..<br />
- Open returns file descriptor that are not allocated..<br />
- 0 is for standard input, 1 is for standard output, 2 is for standard error..<br />

### Read function
Its really important to understand how this function works, because its the key to finish this project.

![image](https://user-images.githubusercontent.com/103336451/221609996-7228f38e-c8c1-4412-be3e-253f46795098.png)

The following video helped me a lot to understand how this project works, but mostly how the read() works.
https://www.youtube.com/watch?v=-Mt2FdJjVno&ab_channel=nikito

### Implementation

1) get_next_line will read a file with the amount of BUFFER_SIZE and determine if the string is a line or not..<br />
2) If the string read is not a line, a function will read a file with same amount again..<br />

3) OPEN_MAX defined in <limits.h>, is the maximum number of files that one process can have open at any one time.
4) Used double pointer to manage strings from n files.
5) Will hold lines read until the program ends.

6) Temporary array that will hold a string read with the amount of BUFFER_SIZE.
7) Will be joined with saved string.

### Testers
To test the code we're going to be using the Francinette  Tester. There are some good others but I'll only be covering this one.

Check the following link to know more about this tester: https://github.com/xicodomingues/francinette

## Final Grade
![image](https://user-images.githubusercontent.com/103336451/221604380-1667b5b0-156b-4b7a-a5ba-202a9baa3b3e.png)
