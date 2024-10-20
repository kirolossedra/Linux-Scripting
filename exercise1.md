# Exercise 1 - Viewing and Modifying File Access Permissions

## 1.1 View File Access Permissions

### Required Files
To download the necessary files for this exercise, run the following commands:

```bash
cd /home/project
wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/module%201/usdoi.txt
```

Each file and directory in your Linux system has permissions set for three categories:
- **User**
- **Group**
- **All users (Other)**

### Permission Symbols
The following permissions are represented by symbols:

| Permission | Symbol |
|------------|--------|
| Read       | r      |
| Write      | w      |
| Execute    | x      |

### Viewing Permissions
To see the current permissions for a file, use the `ls` command with the `-l` option. For example, to view the permissions for the file `usdoi.txt`, enter:

```bash
ls -l usdoi.txt
```

#### Sample Output
A sample output may look like this:

```
-rw-r--r-- 1 theia theia 8121 May 31 16:45 usdoi.txt
```

In this output:
- `-rw-r--r--` indicates the permissions.
- The `-` at the beginning signifies that `usdoi.txt` is a file (a `d` would indicate a directory).
- The first three characters (`rw-`) show the permissions for the user (read and write).
- The next three (`r--`) show the permissions for the group (read only).
- The last three (`r--`) show the permissions for all others (read only).
- No users have execute permissions, as indicated by the absence of `x`.

## 1.2 Change File Access Permissions

### Using `chmod`
The `chmod` (change mode) command allows you to modify file permissions. You can specify which permissions to change using a combination of the following characters:

| Option | Description                     |
|--------|---------------------------------|
| r, w, x| Permissions: read, write, execute |
| u, g, o| User categories: user, group, all others |
| +, -   | Operations: grant (+) and revoke (-) |

### Revoking Permissions
To revoke read permissions for all users on the file `usdoi.txt`, use:

```bash
chmod -r usdoi.txt
```

### Verify Changes
To verify the changed permissions, enter:

```bash
ls -l usdoi.txt
```

### Granting Permissions
To grant read access to all users on `usdoi.txt`, enter:

```bash
chmod +r usdoi.txt
```

### Verify Again
Check the permissions again with:

```bash
ls -l usdoi.txt
```

### Removing Specific Permissions
To remove read permission only for the 'other' category, enter:

```bash
chmod o-r usdoi.txt
```

### Final Verification
Verify the changed permissions once more:

```bash
ls -l usdoi.txt
```
