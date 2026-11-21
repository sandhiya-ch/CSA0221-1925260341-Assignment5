B2 – Engineer Adversarial Inputs

1. Long Donor Name

Test: Enter a donor name longer than the character array.

Expected result: The program should prevent buffer overflow by limiting input length or using "fgets()".

2. Missing Data File

Test: Try opening a file that does not exist.

Expected result: The program should display an error using "perror()".

3. Incorrect Command-Line Arguments

Tests:

- Run without arguments.
- Enter too many arguments.
- Enter an invalid blood group.

Expected result: The program should display a suitable error message and stop safely.

4. Memory Checking

Use AddressSanitizer or Valgrind to check for memory errors.

Expected result: No memory errors or memory leaks should remain after corrections.

5. getline() Alternative

"getline()" can read a line of any length by allocating or resizing memory.

- Time complexity: O(L)
- Space complexity: O(L)
- The allocated memory must be freed using "free()".

Conclusion

Adversarial testing helps identify input errors, file-handling problems and memory issues. Proper validation makes the program safer and more reliable.
