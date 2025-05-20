# C Shell

## Overview

This C Shell implementation provides a variety of built-in commands to manage directories, execute programs, handle background processes, and maintain command history. It is designed to offer a streamlined and user-friendly shell experience.

---

## Features and Functionalities

### 1. 📁 Directory Management

- **Get Current Working Directory**: Displays the current directory path in the shell prompt.
- **Change Directory**: Supports changing directories, including handling `~` for the home directory, `..` for the parent, and `-` for the previous directory.
- **Display Host and Username**: The shell prompt shows the current user and system hostname.

---

### 2. ⚙️ Command Execution

- **Sequential and Background Execution**: Supports executing multiple commands sequentially and in the background using `&`.
- **Custom Command Parsing**: Commands are properly tokenized, trimmed, and executed. Whitespace and tabs are handled cleanly.
- **Command Handler**: Built-in commands are detected and executed internally, while unknown commands are passed to the system.

---

### 3. 🧭 Directory Navigation (`hop` Command)

Navigate through directories with support for:
- `~` → Home directory  
- `..` → Parent directory  
- `-` → Previous directory  

---

### 4. 📂 File and Directory Listing (`reveal` Command)

- Lists files and directories with the following options:
  - `-a` → Include hidden files
  - `-l` → Show detailed information (permissions, size, etc.)
- Outputs are color-coded based on file types.

---

### 5. 📜 Command History (`log` Command)

- Maintains a log of previously executed commands (up to 15), avoiding consecutive duplicates.
- Provides the following options:
  - View command history.
  - Clear all history with `log purge`.
  - Re-execute a command from history using `log execute [n]`.

---

### 6. 🔧 Background Process Management

- Supports running processes in the background with `&`.
- Automatically handles termination of background processes.
- Displays completion messages for finished background jobs.

---

### 7. 🔍 Process Information (`proclore` Command)

- Displays detailed information about a process.
  - Without arguments, shows the current process.
  - With a PID, shows information about the specified process.

---

### 8. 🗃️ File and Directory Search (`seek` Command)

- Allows searching for files and directories with the following options:
  - `-d` → Search for directories
  - `-f` → Search for files
  - `-e` → Execute a file or switch to the found directory

---

## Available Commands

### 🔹 `hop`
Change directories.

```bash
hop [directory]
Examples:

hop ~ → Go to the home directory

hop - → Go to the previous directory

🔹 reveal
List files and directories.

bash
Copy
Edit
reveal [-a] [-l] [directory]
Examples:

reveal -a → Show all files including hidden ones

reveal -l → Show detailed file information

🔹 log
Manage command history.

bash
Copy
Edit
log
log purge
log execute [n]
Examples:

log → Show history

log purge → Clear history

log execute 3 → Run the 3rd most recent command

🔹 proclore
Display process information.

bash
Copy
Edit
proclore [pid]
Examples:

proclore → Show current process info

proclore 1234 → Show info for process with PID 1234

🔹 seek
Search for files or directories.

bash
Copy
Edit
seek [-d] [-f] [-e] target [directory]
Examples:

seek -d myfolder → Search for directory named myfolder

seek -f main.c → Search for file named main.c

seek -e myscript.sh → Execute or open the found file or directory

🚀 Usage
Compile the source code using a C compiler:

bash
Copy
Edit
gcc -o cshell *.c
Run the shell:

bash
Copy
Edit
./cshell
Start using built-in commands:

bash
Copy
Edit
hop ~
reveal -a -l
log execute 2
✅ Conclusion
This C Shell is a functional, feature-rich, and interactive command-line environment. It supports directory navigation, background jobs, detailed file listings, command history, and more — all designed to make shell usage more powerful and efficient.
