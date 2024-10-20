# Exercise 2 - Understanding Directory Access Permissions

## 2.1 View Default Directory Access Permissions

### Directory Permissions Overview
The following table illustrates the meanings of each permission for directories, along with examples of allowable actions:

| Directory Permission | Permissible Action(s)                       |
|----------------------|---------------------------------------------|
| r                    | List directory contents using `ls` command  |
| w                    | Add/remove files or directories from directory |
| x                    | Enter directory using `cd` command          |

### Creating a New Directory
First, move to your project directory and create a new directory called `test`:

```bash
cd /home/project
mkdir test
```

### Check Default Permissions
To check the default permissions set for your new `test` directory, run:

```bash
ls -l
```

#### Sample Output
The resulting output may look like this:

```
total 12
drwxr-sr-x 2 theia users 4096 May 15 14:06 test
-rw-r----- 1 theia users 8121 Sep 28  2022 usdoi.txt
```

### Understanding the Output
- You, as the owner (`theia`), have read, write, and execute permissions on the `test` directory.
- All others only have read and execute permissions, meaning they can list the contents and enter the directory, but cannot add or remove files.
- The `s` in the group permissions indicates a special permission, meaning that new files created within the directory will inherit the group ownership of the directory.

### Verify Permissions
You can verify your permissions by running the following commands:

```bash
cd test
mkdir test2
cd ../
```

## 2.2 Remove User Execute Permissions on Your Test Directory

### Removing Execute Permissions
To remove your user execute permissions on the `test` directory, use:

```bash
chmod u-x test
```

### Attempt to Change Directories
Now, try to change into the `test` directory:

```bash
cd test
```

#### Expected Error
You should receive an error message:

```
bash: cd: test: Permission denied
```

### Reading the Directory
Even though you've removed execute permissions, you can still "read" the directory with the `ls` command:

```bash
ls -l
```

### Attempt to Create a New Directory
You can’t create a new directory within `test` due to the lack of execute permissions, even though you have write permissions. For example:

```bash
mkdir test/test3
```

#### Expected Error
This will throw an error:

```
mkdir: cannot create directory ‘test/test3’: Permission denied
```

### Restore Execute Permissions and Deny Write Permissions
Now, restore execute permissions on `test` and deny write permissions:

```bash
chmod u+x test
chmod u-w test
```

### Verify Changes
Check the permissions again:

```bash
ls -l
```

### Testing Access
You should now be able to enter the `test` directory but not write to it. Try the following commands:

```bash
cd test
mkdir test_again
```

#### Expected Error
You will receive an error message:

```
mkdir: cannot create directory ‘test_again’: Permission denied
``` 

This demonstrates how directory permissions work in Linux, particularly the interplay between read, write, and execute permissions.
