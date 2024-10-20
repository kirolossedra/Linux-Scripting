# Exercise 1 - Create and Execute a Basic Shell Script

In this exercise, you will create a simple shell script that accepts a user name and prints a welcome message. You will also add comments to enhance the script's readability.

## 1.1 Create a New Script File

### Step 1: Create a New File
- In the lab environment, go to **File** -> **New File** to create a new file.

### Step 2: Name the File
- Name the file `greet.sh` and click **OK**.

### Step 3: Add the Script Code
Copy and paste the following lines into the newly created file:

```bash
# This script accepts the user's name and prints 
# a message greeting the user

# Print the prompt message on screen
echo -n "Enter your name: " 

# Wait for user to enter a name, and save it into the variable 'name'
read name 

# Print the welcome message followed by the name
echo "Welcome $name"

# The following message should print on a single line
echo -n "Congratulations! You just created and ran your first shell script "
echo "using Bash on IBM Skills Network"
```

### Step 4: Save the File
- Save the file using **File** -> **Save**.

## 1.2 Execute the Script

### Open a New Terminal
- Click on the menu bar and select **Terminal** -> **New Terminal**. This will open a new terminal at the bottom of the screen.

### Check Permissions
In the newly opened terminal, run the following command to check the permissions for your new script:

```bash
ls -l greet.sh
```

### Execute the Script
If the file exists and has read permissions, execute it using:

```bash
bash greet.sh
```

### User Interaction
- The message `Enter your name:` will appear on the screen. 
- Type your name and press the Enter key.

### Expected Output
You should see the following welcome messages displayed with your entered name:

```
Welcome [Your Name]
Congratulations! You just created and ran your first shell script using Bash on IBM Skills Network
```

Congratulations! You have successfully executed your first Bash shell script.




# Exercise 2 - Using a Shebang Line

In this exercise, you will modify the `greet.sh` script by adding a shebang line and making it an executable file. This allows you to run the script as a command.

## 2.1 Find the Path to the Interpreter
To find the path of the `bash` command, use the `which` command:

```bash
which bash
```

This command should return the path, typically `/bin/bash`.

## 2.2 Edit the Script to Add the Shebang Line
Open the `greet.sh` file and add the following line at the very beginning of the script:

```bash
#! /bin/bash
```

### Updated Script
Your script should now look like this:

```bash
#! /bin/bash
# This script accepts the user's name and prints 
# a message greeting the user

# Print the prompt message on screen
echo -n "Enter your name: " 

# Wait for user to enter a name, and save it into the variable 'name'
read name 

# Print the welcome message followed by the name
echo "Welcome $name"

# The following message should print on a single line
echo -n "Congratulations! You just created and ran your first shell script "
echo "using Bash on IBM Skills Network"
```

## 2.3 Check the Permissions of the Script
To make `greet.sh` executable, you need to add execute permissions for the user. Enter the following command:

```bash
chmod +x greet.sh
```

### Verify Execute Permission
Check whether the execute permission has been granted by running:

```bash
ls -l greet.sh
```

### Limit Execute Permissions
For better security, it’s often best to limit execute permissions to only the owner. To do this, run:

```bash
chmod u+x greet.sh
```

### Verify Permissions Again
Check the permissions again to ensure they are set correctly:

```bash
ls -l greet.sh
```

If you wish to grant execute permission to everyone, you can run:

```bash
chmod +x greet.sh
```

## 2.4 Execute the Script
To run the shell script, enter the following command:

```bash
./greet.sh
```

### Explanation
The `.` here refers to the current directory, telling Linux to execute the `greet.sh` script located in the current directory.

Congratulations! You have successfully added a shebang line and made your script executable.
