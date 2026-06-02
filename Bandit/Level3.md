# Bandit Level 3

## Objective

Use the password obtained from Bandit Level 2 to log in to Bandit Level 3 and find the password for Bandit Level 4.


# Step 1: Log in to Bandit Level 3

In the previous level, we discovered the password for the `bandit3` user.

Using that password, we connect to the Bandit server as `bandit3`.

### Command

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

### General Syntax

```bash
ssh <username>@<hostname> -p <port>
```

After running the command, enter the password obtained from Bandit Level 2.


# Step 2: List Files in the Home Directory

### Command

```bash
ls
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
cd <directory_name>
```

### Explanation

Changes the current working directory.


# Step 4: Display Hidden Files

A normal `ls` command may not show all files.

### Command

```bash
ls -la
```

### General Syntax

```bash
ls -la
```

### Explanation

| Option | Meaning             |
| ------ | ------------------- |
| -l     | Long listing format |
| -a     | Show hidden files   |

### Output

```text
total 12
drwxr-xr-x 2 root    root    4096 Apr  3 15:18 .
drwxr-xr-x 3 root    root    4096 Apr  3 15:18 ..
-rw-r----- 1 bandit4 bandit3   33 Apr  3 15:18 ...Hiding-From-You
```

A hidden file named:

```text
...Hiding-From-You
```

is present in the directory.


# Step 5: Read the Hidden File

### Command

```bash
cat ...Hiding-From-You
```

### General Syntax

```bash
cat <filename>
```

### Explanation

The file is hidden because its name starts with a dot (`.`).

Using the exact filename allows us to read its contents.

### Result

The contents of the file contain the password for Bandit Level 4.

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

### Useful Options

```bash
ls -l
ls -a
ls -la
```

## CD

### Purpose

Change the current directory.

### Syntax

```bash
cd <directory_name>
```

## CAT

### Purpose

Display file contents.

### Syntax

```bash
cat <filename>
```

# New Concept Learned

## Hidden Files

In Linux, files beginning with a dot (`.`) are hidden files.

### Example

```text
.hidden-file
.bashrc
.profile
```

These files are not shown by a normal `ls` command.

To display hidden files:

```bash
ls -a
```

or

```bash
ls -la
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
ls
```

Output:

```text
(no hidden files shown)
```

The hidden file will not be visible.

### Correct

```bash
ls -la
```

Shows all files, including hidden files.

### Incorrect

```bash
cat Hiding-From-You
```

File not found.

### Correct

```bash
cat ...Hiding-From-You
```

Use the exact filename displayed by `ls -la`.


# Key Takeaways

* Used the password from Bandit Level 2 to log in as `bandit3`.
* Learned how to navigate directories using `cd`.
* Learned that files beginning with `.` are hidden files.
* Learned how to view hidden files using `ls -a` and `ls -la`.
* Retrieved the password for Bandit Level 4 from a hidden file.
