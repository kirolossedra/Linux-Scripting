# Exercise 1 - Understand Crontab File Syntax

Cron is a powerful system daemon that executes tasks automatically at specified intervals. Understanding the syntax of a crontab file is essential for scheduling these tasks effectively.

## Crontab File Structure

A crontab file consists of several lines, each representing a scheduled task. The syntax for each line is as follows:

```
* * * * * command_to_execute
```

Where the five asterisks represent time-and-date fields, and `command_to_execute` is the command that will be executed.

### Time-and-Date Fields

Each of the five fields has specific allowed values:

| Field    | Allowed Values             | Description                             |
|----------|----------------------------|-----------------------------------------|
| Minute   | 0-59                       | The minute of the hour                  |
| Hour     | 0-23                       | The hour of the day (0 = midnight)     |
| Day      | 1-31                       | The day of the month                    |
| Month    | 1-12                       | The month (1 = January)                 |
| Weekday  | 0-6                        | The day of the week (0 = Sunday)       |

### Examples

Here are a few examples to illustrate how to schedule tasks:

1. **Run a script every day at 2 AM:**
   ```
   0 2 * * * /path/to/script.sh
   ```

2. **Run a command every hour at the 15th minute:**
   ```
   15 * * * * /path/to/command
   ```

3. **Run a job every Monday at 5 PM:**
   ```
   0 17 * * 1 /path/to/job
   ```

4. **Run a script on the first day of every month at midnight:**
   ```
   0 0 1 * * /path/to/monthly_script.sh
   ```

### Important Notes

- The fields cannot contain spaces; they must be separated by a single space.
- Comments can be added to a crontab file by starting the line with a `#`.
- It is essential to ensure that the command paths are correct and executable permissions are set.

By understanding this syntax, you can effectively automate tasks on your system using cron.




# Exercise 2 - List Cron Jobs

## Step 1: Open a Terminal
1. Open a new terminal by clicking on the menu bar and selecting **Terminal** > **New Terminal**.
2. This will open a new terminal window.

## Step 2: List Current Cron Jobs
Run the following command to list the current cron jobs:

```bash
crontab -l
```

- If you see the message "no crontab for theia," it means your crontab is currently empty.

---

# Exercise 3 - Add a Job in the Crontab File

## 3.1 Add a Cron Job
### Step 1: Edit the Crontab
To add a new cron job, run:

```bash
crontab -e
```

- This command opens your crontab file in an editor. 

### Step 2: Add the Cron Job
Scroll down to the end of the file using the arrow keys and add the following line:

```bash
0 21 * * * echo "Welcome to cron" >> /tmp/echo.txt
```

- This job runs at 9:00 PM every day and appends the message "Welcome to cron" to the file `/tmp/echo.txt`.

### Step 3: Save and Exit
- Press `Ctrl + X` to save the changes.
- Press `Y` to confirm.
- Press `Enter` to exit the editor.

### Step 4: Verify the Job is Added
Check if the job was added successfully by running:

```bash
crontab -l
```

- You should see the newly added job in the output.

---

## 3.2 Schedule a Shell Script

### Step 1: Create the Shell Script
1. Use the menu to select **File** > **New File**.
2. Name the file `diskusage.sh` and click **OK**.

### Step 2: Add Script Content
Copy and paste the following commands into the `diskusage.sh` file:

```bash
#!/bin/bash
# Print the current date and time
date
# Print the disk free statistics
df -h
```

### Step 3: Save the File
Save the file using **File** > **Save**.

### Step 4: Verify the Script Works
Run the following commands to make the script executable and test it:

```bash
chmod u+x diskusage.sh
./diskusage.sh
```

- The script should print the current timestamp and disk usage statistics.

### Step 5: Schedule the Script
To schedule this script to run every day at midnight (12:00 AM) and append the output to `/home/project/diskusage.log`, edit the crontab again:

```bash
crontab -e
```

Add the following line to the end of the file:

```bash
0 0 * * * /home/project/diskusage.sh >> /home/project/diskusage.log
```

### Step 6: Save and Exit
- Press `Ctrl + X`, then `Y`, and `Enter` to save and exit.

### Step 7: Verify the Job is Added
Run the command again to check if the new job was added:

```bash
crontab -l
```

---

# Exercise 4 - Remove the Current Crontab

## Step 1: Remove the Crontab
To remove your current crontab (be cautious, as this will delete all your cron jobs), run:

```bash
crontab -r
```

## Step 2: Verify the Crontab is Removed
Check to ensure your crontab has been removed by running:

```bash
crontab -l
```

- You should see the message "no crontab for theia" if the removal was successful.
