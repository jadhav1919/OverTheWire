# Bandit Level 4

## Objective

Use the password obtained from Bandit Level 3 to log in to Bandit Level 4 and find the password for Bandit Level 5.

# Step 1: Log in to Bandit Level 4

In the previous level, we discovered the password for the `bandit4` user.

Using that password, we connect to the Bandit server as `bandit4`.

### Command

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

After running the command, enter the password obtained from Bandit Level 3.


# Step 2: Examine the Home Directory

### Command

```bash
ls -la
```

### Output

```text
inhere
```

A directory named `inhere` is present.

# Step 3: Move into the Directory

### Command

```bash
cd inhere
```

### General Syntax

```bash
cd <directory>
```

### Explanation

Changes the current working directory.


# Step 4: List the Files

### Command

```bash
ls -la
```

### Output

```text
-file00
-file01
-file02
-file03
-file04
-file05
-file06
-file07
-file08
-file09
```

The directory contains multiple files.

The challenge description states that only one file is human-readable.

# Step 5: Determine the File Types

### Command

```bash
file ./-file*
```

### General Syntax

```bash
file <filename>
```

### Explanation

The `file` command identifies the type of a file by examining its contents.

### Breakdown

| Part   | Meaning                                  |
| ------ | ---------------------------------------- |
| file   | Determine file type                      |
| ./     | Current directory                        |
| -file* | Matches all files beginning with `-file` |

### Output

```text
./-file00: data
./-file01: data
./-file02: data
./-file03: DOS executable
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
```

The only human-readable file is:

```text
-file07
```

because it is identified as:

```text
ASCII text
```

# Step 6: Read the Human-Readable File

### Command

```bash
cat ./-file07
```

### Explanation

Displays the contents of the identified text file.

### Result

The file contains the password for Bandit Level 5.


# Commands Used

## LS

### Purpose

List files and directories.

### Syntax

```bash
ls [options] [directory]
```


## CD

### Purpose

Change the current directory.

### Syntax

```bash
cd <directory>
```

## FILE

### Purpose

Determine the type of a file.

### Syntax

```bash
file <filename>
```

### Examples

```bash
file notes.txt
file image.png
file program.exe
```

## CAT

### Purpose

Display file contents.

### Syntax

```bash
cat <filename>
```

# New Concept Learned

## File Type Identification

The `file` command determines what kind of data a file contains.

Examples:

```text
ASCII text
data
PNG image
PDF document
DOS executable
```

This is useful when filenames do not clearly indicate their contents.


# Commands Mentioned by OverTheWire

| Command | Purpose                          |
| ------- | -------------------------------- |
| ls      | List files and directories       |
| cd      | Change directory                 |
| cat     | Display file contents            |
| file    | Determine file type              |
| du      | Display disk usage               |
| find    | Search for files and directories |


# Common Mistakes

### Incorrect

```bash
cat ./-file00
```

This displays unreadable data or incorrect content.

### Correct

```bash
file ./-file*
```

First identify the human-readable file.

### Then

```bash
cat ./-file07
```

Read the correct file.
```bash
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

# Key Takeaways

* Used the password from Bandit Level 3 to log in as `bandit4`.
* Learned how to identify file types using the `file` command.
* Learned how wildcard characters (`*`) can match multiple files.
* Learned how to locate a human-readable file among many files.
* Retrieved the password for Bandit Level 5.
