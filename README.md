# C Shell

## Overview

This C Shell implementation provides a variety of features and functionalities to manage directories, execute commands, handle background processes, and maintain command history.

## Features and Functionalities

### 1. Directory Management

- Get Current Working Directory
  - Retrieves the current working directory and displays it in the shell prompt.

- Change Directory
  - Changes the current working directory to the specified path.
  - Handles special cases like `~` and `...`.

- Get Hostname
  - Retrieves the hostname of the system for display in the prompt.

- Get Username
  - Retrieves the username of the current user for display in the prompt.

### 2. Command Handling

- Command Processing
  - Tokenizes the input command string and executes each command sequentially.
  - Supports background execution using `&`.

- Command Routing
  - Routes commands to the appropriate handler based on the command name.

- Input Processing
  - Removes leading and trailing whitespace from user input.

### 3. Directory Navigation

- Directory Hopping
  - Provides an intuitive way to navigate directories.
  - Supports special cases like `~` (home directory) and `-` (previous directory).

### 4. File and Directory Listing

- File and Directory Display
  - Lists files and directories in a clear format.
  - Supports flags `-a` for all files (including hidden) and `-l` for detailed information.

- Detailed Information Display
  - Shows detailed information about files and directories including permissions, size, and timestamps.

- Color Coding
  - Displays file and directory names with color coding based on their type for better readability.

### 5. Command History

- History Management
  - Loads and saves command history for persistence between sessions.
  - Avoids duplicate entries in the history.

- History Display
  - Shows the command history with numbering for easy reference.

- Input Normalization
  - Removes unnecessary spaces and tabs from commands before adding to history.

- History Manipulation
  - Provides commands to clear history and re-execute commands from history.

### 6. Background Process Management

- Signal Handling
  - Sets up proper signal handling for background processes.

- Process Tracking
  - Maintains a list of background processes for monitoring.
  - Handles process cleanup when background processes terminate.

- Background Execution
  - Allows commands to be executed in the background with the `&` operator.

### 7. Process Information

- Process Details
  - Displays detailed information about processes including state, memory usage, etc.

### 8. File Search

- File and Directory Search
  - Searches for files and directories matching specified criteria.
  - Supports flags `-d` for directories, `-f` for files, and `-e` for executing or changing to found items.

## Available Commands

### hop

- **Description**: Changes the current directory.
- **Usage**: `hop [directory]`
- **Examples**:
  - `hop ~` - Changes to the home directory.
  - `hop -` - Changes to the previous directory.

### reveal

- **Description**: Lists files and directories.
- **Usage**: `reveal [-a] [-l] [directory]`
- **Examples**:
  - `reveal -a` - Lists all files including hidden ones.
  - `reveal -l` - Lists files with detailed information.

### log

- **Description**: Manages command history.
- **Usage**:
  - `log` - Prints the command history.
  - `log purge` - Clears the command history.
  - `log execute [n]` - Re-executes the nth command from history.

### proclore

- **Description**: Displays detailed information about a process.
- **Usage**: `proclore [pid]`
- **Examples**:
  - `proclore` - Displays information about the current process.
  - `proclore 1234` - Displays information about the process with PID 1234.

### seek

- **Description**: Searches for files and directories.
- **Usage**: `seek [-d] [-f] [-e] target [directory]`
- **Examples**:
  - `seek -d target` - Searches for directories matching the target.
  - `seek -f target` - Searches for files matching the target.
  - `seek -e target` - Executes or changes to the found file or directory.

## Usage

To use this C Shell, compile the source files and run the resulting executable. The shell supports various built-in commands as described above. For example:

- `hop ~` to change to the home directory.
- `reveal -a -l` to list all files and directories with detailed information.
- `log purge` to clear the command history.
- `seek -d target` to search for directories matching the target.

## Conclusion

This C Shell provides a comprehensive set of features for managing directories, executing commands, handling background processes, and maintaining command history. It is designed to be a functional and user-friendly shell environment.
