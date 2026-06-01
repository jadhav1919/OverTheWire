# Bandit Level 0

## Objective

Connect to the Bandit server and find the password for Bandit Level 1.

---

# Step 1: Connect to the Server

Command:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

## General Format

```bash
ssh <username>@<hostname> -p <port>
```

### Explanation

| Part | Meaning |
|--------|---------|
| ssh | Secure Shell program used to connect to remote systems |
| username | Account you want to log in as |
| hostname | Address of the remote machine |
| -p | Specifies the port number |
| 2220 | Port used by the Bandit server |

### In This Level

- Username: bandit0
- Host: bandit.labs.overthewire.org
- Port: 2220

After running the command, enter the password:

```text
bandit0
```

---

# Step 2: List Files

Command:

```bash
ls
```

## General Format

```bash
ls [options] [directory]
```

### Explanation

| Part | Meaning |
|--------|---------|
| ls | Lists files and directories |
| options | Optional flags such as -l or -a |
| directory | Optional path to inspect |

### In This Level

```bash
ls
```

Output:

```text
readme
```

This shows there is a file named `readme`.

---

# Step 3: Read the File

Command:

```bash
cat readme
```

## General Format

```bash
cat <filename>
```

### Explanation

| Part | Meaning |
|--------|---------|
| cat | Displays file contents |
| filename | File to display |

### In This Level

```bash
cat readme
```

This displays the password for Bandit Level 1.

---

# Commands Learned

## SSH

Purpose:

Connect to a remote machine.

General Syntax:

```bash
ssh <username>@<hostname> -p <port>
```

---

## LS

Purpose:

List files and directories.

General Syntax:

```bash
ls [options] [directory]
```

Useful Options:

```bash
ls -l
ls -a
ls -la
```

---

## CAT

Purpose:

Display file contents.

General Syntax:

```bash
cat <filename>
```

---

# Key Takeaways

- Learned how to connect to a remote Linux server using SSH.
- Learned how to list files in a directory.
- Learned how to read file contents.
- Obtained the password for the next level.
