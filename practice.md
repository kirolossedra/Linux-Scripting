# Practice Exercises

## 1. List the Permissions for the File `usdoi.txt`
To list the permissions set for the file `usdoi.txt`, run the following command:

```bash
ls -l usdoi.txt
```

## 2. Revoke Write Permission on `usdoi.txt` for the User
To revoke write permission for the user on `usdoi.txt`, use:

```bash
chmod u-w usdoi.txt
```

### Verify Your Result
Check the permissions again to confirm the change:

```bash
ls -l usdoi.txt
```

## 3. Attempt to Delete `usdoi.txt` After Revoking Write Permissions
After revoking write permissions, try to delete the file:

```bash
rm usdoi.txt
```

### Expected Outcome
You will receive an error message indicating that permission is denied because you no longer have write access.

## 4. Create a New Directory Called `tmp_dir`
To create a new directory named `tmp_dir` in your home directory, run:

```bash
mkdir ~/tmp_dir
```

## 5. View Permissions of the Newly Created Directory
To check the permissions of the `tmp_dir`, use:

```bash
ls -l ~/tmp_dir
```

## 6. Revoke User Write Permission for `tmp_dir`
To revoke write permission for the user on `tmp_dir`, use:

```bash
chmod u-w ~/tmp_dir
```

## 7. Check Whether You Can Create a Subdirectory Called `sub_dir`
Try to create a subdirectory within `tmp_dir` named `sub_dir`:

```bash
mkdir ~/tmp_dir/sub_dir
```

### Expected Outcome
You will receive an error message indicating that permission is denied because you do not have write permissions for `tmp_dir`.
