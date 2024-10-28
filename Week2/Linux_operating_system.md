# What is Linux?

**Operating system** is software that manages the commnunication between software and hardware system in the computer. Just like Windows, iOS, and Mac OS, Linux is an operating system. One of the most popular platform, Android, is lso powered by linux operating system.

## Philosophy


Linux is built on a philosophy that emphasizes simplicity, flexibility, and user control, encapsulated in its five core principles:

1. **Everything is a File**: In Linux, everything is treated as a file, from hardware devices to system configurations. This principle unifies the operating system’s design, simplifying management. Configuration for services and applications is typically stored in readable text files, which makes troubleshooting and editing straightforward.

2. **Small, Single-Purpose Programs**: Linux provides a suite of small, dedicated tools, each designed for a specific task. This modularity allows users to choose the best tools for their needs and combine them for maximum efficiency, enhancing both performance and ease of maintenance.

3. **Ability to Chain Programs Together for Complex Tasks**: Linux enables powerful workflow creation by allowing programs to work together. Using “pipes,” users can pass the output of one program as the input to another, chaining tools to perform complex, multi-step tasks, such as data processing and filtering.

4. **Avoid Captive User Interfaces**: Linux emphasizes a command-line-based interface, which maximizes user control. By using the shell, users have deeper and more flexible access to the system than graphical interfaces usually allow, providing enhanced control over configurations and scripts.

5. **Configuration Data Stored in Text Files**: Configuration files, often located in directories like `/etc`, store essential system data in plain text, making it easy for users to access, modify, or back up system settings. For instance, the `/etc/passwd` file contains information about users on the system, which can be edited directly, further underscoring Linux's transparency and accessibility.

## Components

Linux is made up of several core components, each playing a specific role in the functionality of the operating system. Here's an overview of these components:

1. **Bootloader**: This is the initial program that loads during the computer's boot-up process. It guides the system in starting the operating system. Parrot Linux, for example, uses the GRUB bootloader, which provides users with options to choose the operating system they want to load.

2. **OS Kernel**: The kernel is the core of Linux, responsible for managing hardware resources and enabling software interactions with hardware devices. It handles crucial tasks, like managing system memory, CPU allocation, and I/O device interactions, serving as the foundation for all other system components.

3. **Daemons**: Known as background services, daemons support essential system functions and run behind the scenes. They handle tasks such as system scheduling, printing, and media services. These daemons start either during boot or upon logging in, ensuring the system operates smoothly and efficiently.

4. **OS Shell**: The shell, or command-line interface, provides an interface between the user and the operating system, allowing users to issue commands and automate tasks. Linux offers several popular shells, such as Bash, Tcsh/Csh, Ksh, Zsh, and Fish, each with unique features tailored to different user preferences.

5. **Graphics Server**: This component enables graphical applications to run by managing the graphical sub-system. The “X-server” (or simply “X”) provides the foundational graphical layer for Linux, supporting local or remote execution of graphical programs within the X-windowing system.

6. **Window Manager**: This is the graphical user interface (GUI) component of Linux, providing users with an intuitive way to interact with applications and manage files visually. Popular options include GNOME, KDE, MATE, Unity, and Cinnamon, each offering unique layouts and features. These environments come with built-in applications like file managers and web browsers, streamlining daily interactions with the OS.

7. **Utilities**: Linux utilities are the applications and tools designed to perform specific tasks, ranging from file management to system monitoring. These utilities support both users and programs, contributing to the system's overall functionality and customization.

## Linux Architecture


Linux architecture is structured in layers, each providing a distinct function that builds upon the other to deliver a fully operational system. Here’s a breakdown of each layer:

1. **Hardware**: This is the foundational layer that includes all physical components of the system, such as the CPU, RAM, hard drive, and other peripherals. These devices provide the resources that the operating system will manage and utilize.

2. **Kernel**: The kernel is the core of the Linux operating system. It plays a critical role by abstracting and managing the hardware resources for applications, including CPU time, memory allocation, and data access. The kernel ensures that each process has its own virtual resources and works to prevent conflicts, making sure that the system remains stable and efficient.

3. **Shell**: The shell is the command-line interface (CLI) through which users interact with the Linux kernel. By entering commands into the shell, users can directly control various functions of the kernel, enabling them to manage files, execute programs, and access system utilities.

4. **System Utility**: This layer provides a collection of tools and applications that make the full functionality of the Linux operating system accessible to the user. These utilities allow users to manage files, monitor system performance, and perform a wide range of administrative tasks.


## Linux command Line
File in the linux system are arranged in a hierarchical directory structure(in a tree-like pattern in directories) 

##### Root
- Most root or the basic directory in linux is a root directory
- Reprensented with forward slash (/)


##### pwd (present working directory)
- this showa you which directory you are currently working in.

![alt text](<Images/Screenshot from 2024-09-24 21-43-12.png>)

##### cd (change dirctory)

![alt text](<Images/Screenshot from 2024-09-24 21-46-28.png>)

##### echo
- Output any text that we provide

![alt text](<Images/Screenshot from 2024-10-08 08-34-39.png>)

##### whoami
- Find out what user we're currently logged in as.

![alt text](<Images/Screenshot from 2024-10-08 08-36-53.png>)

#####  Grep
- command-line tool that is used for searching plain-text data sets for lines matching a regular expression.


### Basic Syntax
```bash
grep [options] pattern [file...]
```

### Common Options

- **Basic Search:**
  ```bash
  grep "pattern" filename
  ```
  Searches for "pattern" in the specified file.

- **Recursive Search (`-r` or `-R`):**
  ```bash
  grep -r "pattern" /path/to/directory
  ```
  Searches for "pattern" in all files within the specified directory and subdirectories.

- **Ignore Case (`-i`):**
  ```bash
  grep -i "pattern" filename
  ```
  Case-insensitive search.

- **Show Line Numbers (`-n`):**
  ```bash
  grep -n "pattern" filename
  ```
  Displays line numbers with each matching line.

- **Count Matches (`-c`):**
  ```bash
  grep -c "pattern" filename
  ```
  Counts the number of lines that match the pattern in the specified file.

- **Match Whole Words (`-w`):**
  ```bash
  grep -w "word" filename
  ```
  Matches whole words only, not substrings.

- **Invert Match (`-v`):**
  ```bash
  grep -v "pattern" filename
  ```
  Shows lines that do *not* match the pattern.

### Advanced Usage

- **Using Regular Expressions (`-E` for Extended):**
  ```bash
  grep -E "pattern1|pattern2" filename
  ```
  Searches for multiple patterns.

- **Print Only Matching Part (`-o`):**
  ```bash
  grep -o "pattern" filename
  ```
  Shows only the matching parts, not the entire line.

### Example Usage

To find lines containing the word "error" (case-insensitive) in all `.log` files in a directory:
```bash
grep -ri "error" *.log
```
## Linux Operator

##### Operator "&"
- This operator allows  to run commands in the background of your terminal.

##### Operator "&&"
- This operator allows you to combine multiple commands together in one line of your terminal.

##### Operator ">"
- This operator is a redirector - meaning that we can take the output from a command (such as using cat to output a file) and direct it elsewhere.

##### Operator ">>"
- This operator does the same function of the > operator but appends the output rather than replacing (meaning nothing is overwritten).

#### Note
**Shell** - the shell is a program that takes command from the keyboard and gives them to operating system to perform.

**Terminal** - is a tool which we can use to pass our shell commands. It is a program which opens window and let us interact with the shell.


# Why use Linux?
 
**Linux** has evolved into one of the most reliable computer ecosystems. Combine that reliability with zero cost of entry and we have the perfect solution for a desktop platform.

Linux is also distributed under an open source license. Open source follows these key tenets:

- The freedom to run the program.
- The freedom to study how the program works, and change it to make it do what you wish.
- The freedom to redistribute copies.
- The freedom to distribute copies of your modified versions to others.

 Linux is an operating system famously known as “by the people, for the people”.  It’s about freedom and freedom of use and freedom of choice.

# Kali Linux
**Kali Linux** (formerly known as BackTrack Linux) is an open-source, Debian-based Linux distribution which allows users to perform advanced penetration testing and security auditing. 

#### Kali Linux Features
- Kali linux is free 
- All of the source code which goes into Kali Linux is available for anyone who wants to tweak or rebuild packages to suit their specific needs.
-  Linux users can easily locate binaries, support files, libraries, and so on.
-  Kali supports a wide variety of hardware and as many wireless devices as possible, including USB-based devices.
 - As penetration testers, the development team often needs to do wireless assessments, so our kernel has the latest injection patches included.
 - Developed in a secure environment
 
 References- What is Linux? - Linux.com. (2022, August 26).