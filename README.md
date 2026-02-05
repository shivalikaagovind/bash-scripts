# Bash Scripts

This repository contains Bash scripts developed for looking at test cases and running automated input/output–based tests.

---
## `testDescribe` file

The script `testDescribe` processes a file containing a list of file stems where each file stem is a test case. 
This script demonstrates safe file handling, iteration over whitespace-separated input, and conditional logic in Bash.

This script expects **one command-line argument**:
1. test set file containing stems to other files

The script:
- Prints a usage message to **stderr** if no argument is provided
- Iterates through each stem in the test set file
- Goes to the file stem and prints the contents

---

## `runInTests` file

The script `runInTests` automates testing of programs using redirected input and output comparison.
This script introduces input/output redirection, exit status checking, and automated test validation.

This scrip expects **two command-line arguments**:
1. A command to execute (e.g. `wc`)
2. A test set file containing file stems

The script: 
- Runs the given command with input in the stem file
- Captures the program’s output into a temporary file
- Compares the output of the command to the expected output stored in a different file
- States if the test passed or failed
- If the test failed, the acutal and expected outcomes are stated

---

## `runTests` file

The script `runTests` extends `runInTests` by supporting **command-line arguments for test case**.

This scrip expects **two command-line arguments**:
1. A command to execute (e.g. `wc`)
2. A test set file containing file stems

The script (differences from `runInTests`:
- Navigates to second argument in the test set file
- Inserts the argument directly in the command invocation
- Executes the command with the additional commnad line arguments

---

## Improvements

The following are improvements that can me made to my code
1. More error handeling. For example, checking if command line arguments are correctly provided and if the given command line arguments are valid.
2. In addition to my first point, there can be stronger error reporting. When these errors do occur, the user should be given a message.
3. Improved whitespace and formatting control 



