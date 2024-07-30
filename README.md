# TinyShell(C_Linunx_Terminal)

## Description
`TinyShell` is a minimalist Linux terminal emulator implemented in C. It aims to provide a simplified yet functional command-line interface for executing basic shell commands and managing processes. This project demonstrates fundamental concepts of process control, inter-process communication, and command execution in a Unix-like operating system environment.

## Features
- Basic shell prompt
- Command execution with support for foreground and background processes
- Process control with job listing
- Built-in commands such as `cd`, `exit`,`ls`,`sleep`, and `history`

## Files and Directories
- **`main.c`**: The main entry point of the shell, responsible for initializing the shell and handling user input.
- **`prompt.c`**: Handles displaying the shell prompt.
- **`foreback.c`**: Manages foreground and background process execution.
- **`pastevents.c`**: Manages history and listing of past commands.
- **`peek.c`**: Contains functions for visualizing the file and directory structure.
- **`proclore.c`**: Function to get all information of a particular process.
- **`seek.c`**: Additional utility functions implimenting `ls` feature.
- **`warp.c`**: Additional utility functions implimenting `cd` feature.
- **Header Files** (`*.h`): Provide declarations for corresponding C files.
- **`makefile`**: Automates the build process for the project.
- **`README.md`**: Contains project documentation.

## Installation
1. Clone the repository:
    ```sh
    git clone https://github.com/Samarth23-sudo/C_Linux_Terminal
    cd C_Linux_Terminal
    ```

2. Build the project:
    ```sh
    make
    ```

## Usage
Run the shell:
```sh
./myshell
