# TinyShell(C_Linunx_Terminal)

## Description
`TinyShell` is a minimalist Linux terminal emulator implemented in C. It aims to provide a simplified yet functional command-line interface for executing basic shell commands and managing processes. This project demonstrates fundamental concepts of process control, inter-process communication, and command execution in a Unix-like operating system environment.

## Features
- Basic shell prompt
- Command execution with support for foreground and background processes
- Process control with job listing
- Built-in commands such as `cd`, `exit`,`ls`,`sleep`, and `history`

## Commands

### warp
Similar to `cd` in Bash, `warp` allows you to navigate directories with additional features.

**Features:**
- Supports `.`, `..`, `~`, and `-` like in Bash.
- Defaults to the home directory if no arguments are given.
**Usage:**
warp <path1> <path2 inside path1>   

### peek
Lists all the files and directories in the specified directory in lexicographic order.

**Features:**
- By default, does not show hidden files.
- Supports `.` `..`, `~` flags.
- Supports both relative and absolute paths.
- Displays color-coded files: blue for directories, cyan for symbolic links, green for executables, and white for other files.
- If no arguments are given, peeks at the current working directory.

**Usage:**
peek <flags> <path>

**Flags:**
- `-l`: Displays extra information about each file (similar to `ls -l`).
- `-a`: Displays hidden files (similar to `ls -a`).

### pastevents
Similar to the `history` command in Bash. Stores and outputs the last 15 most recent command statements input to the shell.

**Features:**
- Persistent storage over different shell runs.
- Does not store a command if it is exactly the same as the previously entered command.
- Stores all statements except those that include `pastevents` or `pastevents purge`.

**Sub-commands:**
- `pastevents purge`: Clears all stored pastevents.
- `pastevents execute <index>`: Executes the command at the specified position in pastevents (1-indexed).

**Usage:**
pastevents
pastevents purge
pastevents execute <index>

### proclore
Used to obtain information regarding a process. Prints information about the shell if no argument is given.

**Information Printed:**
- `pid` (Process ID)
- Process Status (R/R+/S/S+/Z)
- Process Group (Process Group ID)
- Virtual Memory (in bytes)
- Executable Path (relative to the home directory of the shell, if valid)

**Usage:**
proclore <pid>

### seek
Looks for a file/directory in the specified target directory (or current working directory, if no directory is specified).

**Features:**
- Returns a list of relative paths of all matching files/directories which have the specified prefix.
- Handles permissions warnings and proceeds if possible.
- Prints "No match found!" if no match is found.
- Supports color-coding: blue for directories and green for other files.

**Flags:**
- `-d`: Looks only for directories.
- `-f`: Looks only for files.
- `-e`: Effective only when a single file or directory with the name is found; prints the contents or changes the directory.

**Usage:**
seek <flags> <search_prefix> <target_directory>

### activities
Prints a list of all the processes currently running that were spawned by the shell in lexicographic order.

**Output Format:**
[pid]: [command name] - [state]

**States:**
- Running: Any process that hasn't stopped.
- Stopped: A process that has stopped.

**Usage:**
activities


## Files and Directories
- **`main.c`**: The main entry point of the shell, responsible for initializing the shell and handling user input.
- **`prompt.c`**: Handles displaying the shell prompt.
- **`foreback.c`**: Manages foreground and background process execution.
- **`pastevents.c`**: Manages history and listing of past commands.
- **`peek.c`**: Implimentation of `peek` feature.
- **`proclore.c`**: Implimentation of `proclore` feature.
- **`seek.c`**: Implimentation of `seek` feature.
- **`warp.c`**: Additional utility functions implimenting `cd` feature.
- **Header Files** (`*.h`): Provide declarations for corresponding C files.
- **`makefile`**: Automates the build process for the project.
- **`README.md`**: Contains project documentation.

## Installation
1. Clone the repository:
    ```sh
    git clone https://github.com/Samarth23-sudo/TinyShell
    cd TinyShell
    ```

2. Build the project:
    ```sh
    make
    ```

## Usage
Run the shell:
```sh
./myshell
