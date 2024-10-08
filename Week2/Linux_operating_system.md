# What is Linux?

**Operating system** is software that manages the commnunication between software and hardware system in the computer. Just like Windows, iOS, and Mac OS, Linux is an operating system. One of the most popular platform, Android, is lso powered by linux operating system.


The Linux operating system comprises several different pieces:

1. **Bootloader -** The software that manages the boot process of a computer. For most users, this will simply be a splash screen that pops up and eventually goes away to boot into the operating system.

2. **Kernel –** The kernel is the core of the system and manages the CPU, memory, and peripheral devices. The kernel is the lowest level of the OS.

3. **Init system –** It is the init system that manages the boot process, once the initial booting is handed over from the bootloader.

4. **Daemons –** These are background services (printing, sound, scheduling, etc.) that either start up during boot or after you log into the desktop.

5. **Graphical server –** This is the sub-system that displays the graphics on your monitor. It is commonly referred to as the X server or just X.

6. **Desktop environment –** This where the user interat with. There are many desktop environments to choose from like GNOME, Cinnamon, Mate, Pantheon, Enlightenment, KDE, Xfce, etc.

7. **Applications –** Linux offers thousands upon thousands of high-quality software titles that can be easily found and installed.

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