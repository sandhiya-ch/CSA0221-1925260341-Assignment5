B2 – Engineer Adversarial Inputs

1. Objective

To test the program using long names, missing files, incorrect command-line arguments and memory checking tools.

2. Test 1 – Long Donor Name

Using scanf("%s"):

- A donor name longer than the character array may cause a buffer overflow.
- It can overwrite nearby memory and cause unexpected behaviour.

Using fgets():

- fgets() limits the number of characters read.
- It helps prevent writing beyond the array size.
- It is safer for reading donor names.

3. Test 2 – Missing or Read-Only File

When a file cannot be opened, the program should use perror() to display the error.

Example:

FILE *fp = fopen("donors.dat", "r");

if (fp == NULL) {
    perror("File opening failed");
    return 1;
}

4. Test 3 – Incorrect Command-Line Arguments

Input| Expected behaviour
No arguments| Display usage message
Too many arguments| Display invalid argument message
Invalid blood group| Display error message

The program should validate arguments before performing operations.

5. Test 4 – Memory Checking

The program can be checked using AddressSanitizer.

Command:

gcc -fsanitize=address -g program.c -o program
./program

AddressSanitizer helps detect memory errors such as buffer overflows and use-after-free errors.

6. Corrections

1. Use fgets() instead of unsafe input using scanf("%s").
2. Check whether fopen() returns NULL.
3. Validate command-line arguments.
4. Free dynamically allocated memory after use.
5. Check memory errors using AddressSanitizer.

7. Result

Adversarial testing helps identify unsafe input handling, file errors, invalid arguments and memory problems. Input validation and proper error handling make the program safer and more reliable.
