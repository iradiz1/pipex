# Pipex

## Introduction
Pipex is a project aimed at implementing a simplified version of the shell pipe mechanism in Unix-like operating systems using C. The goal is to execute a series of commands and redirect the output of one command as input to another command, simulating the behavior of the `|` operator in shell scripting.

## Description
The pipex program takes a series of arguments, including two commands and filenames for input and output. It then executes the commands in two different child processes and establishes a unidirectional pipe between them, allowing the output of the first command to be passed as input to the second command. The final result is written to the specified output file.

## Implementation
The project is implemented in C, utilizing system calls such as `fork()`, `exec()`, and `pipe()` for process creation, program execution, and inter-process communication. Error handling and edge cases, such as file existence and permission checks, are also implemented to ensure robustness.

## Usage
To compile the program, run the following command in your terminal:

make

To run the program, execute the compiled binary with the required arguments:

./pipex file1 cmd1 cmd2 file2

- `file1`: Input file whose content will be passed to `cmd1`.
- `cmd1`: First command to be executed.
- `cmd2`: Second command to be executed.
- `file2`: Output file where the final result will be stored.

For example:

./pipex infile "ls -l" "wc -l" outfile

This command will execute `ls -l` to list files in the current directory and then execute `wc -l` to count the number of lines in the output of the first command. The final result will be stored in `outfile`.