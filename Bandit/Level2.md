# Bandit Level 2

## Objective

Use the password obtained from Bandit Level 1 to log in to Bandit Level 2 and find the password for Bandit Level 3.

# Step 1: Log in to Bandit Level 2

In the previous level, we discovered the password for the `bandit2` user.

Using that password, we connect to the Bandit server as `bandit2`.

### Command

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

### General Syntax

```bash
ssh <username>@<hostname> -p <port>
```

### Explanation

| Part     | Meaning                            |
| -------- | ---------------------------------- |
| ssh      | Secure Shell client                |
| username | User account to log in as          |
| hostname | Remote server address              |
| -p       | Specifies the port number          |
| 2220     | SSH port used by the Bandit server |

After running the command, enter the password obtained from Bandit Level 1.

# Step 2: Examine the Current Directory

List the files present in the current directory.

### Command

```bash
ls -la
```

### General Syntax

```bash
ls [options] [directory]
```

### Explanation

The `-la` options display:

| Option | Meaning             |
| ------ | ------------------- |
| -l     | Long listing format |
| -a     | Show hidden files   |

### Output

```text
--spaces in this filename--
```

A file exists whose name contains spaces and begins with `--`.

# Step 3: Initial Attempt

A common first attempt is:

```bash
cat "spaces in this filename"
```

### Result

```text
cat: 'spaces in this filename': No such file or directory
```

This failed because the actual filename is:

```text
--spaces in this filename--
```

# Step 4: Read the File Correctly

Since the filename contains spaces and starts with `--`, we need to specify the file path explicitly.

### Command

```bash
cat ./--spaces\ in\ this\ filename--
```

### Explanation

| Part                        | Meaning                         |
| --------------------------- | ------------------------------- |
| cat                         | Display file contents           |
| ./                          | Refers to the current directory |
| \                           | Escapes spaces in the filename  |
| --spaces in this filename-- | Actual filename                 |

### Alternative Command

```bash
cat "./--spaces in this filename--"
```

Both commands work correctly.


# Step 5: Retrieve the Password

### Output

```text
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

This is the password for Bandit Level 3.


# Commands Used

## SSH

### Purpose

Connect to a remote Linux machine.

### Syntax

```bash
ssh <username>@<hostname> -p <port>
```

## LS

### Purpose

List files and directories.

### Syntax

```bash
ls [options] [directory]
```

## CAT

### Purpose

Display file contents.

### Syntax

```bash
cat <filename>
```

# New Concepts Learned

## Filenames Containing Spaces

Spaces separate command arguments in Linux.

To treat spaces as part of a filename:

```bash
cat file\ name
```

or

```bash
cat "file name"
```
## Relative Paths

### Syntax

```bash
./<filename>
```

### Purpose

Refers to a file in the current directory.

Useful when filenames begin with special characters such as:

```text
-
--
$
*
?
!
```

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
cat spaces in this filename
```

Linux interprets each word as a separate argument.

### Incorrect

```bash
cat "spaces in this filename"
```

The filename is incomplete.

### Correct

```bash
cat ./--spaces\ in\ this\ filename--
```

### Correct

```bash
cat "./--spaces in this filename--"
```

# Key Takeaways

* Used the password from Bandit Level 1 to log in as `bandit2`.
* Learned how Linux handles filenames containing spaces.
* Learned how to escape spaces using the `\` character.
* Learned how to use quotation marks around filenames.
* Learned how to use `./` to reference files in the current directory.
* Obtained the password for Bandit Level 3.
