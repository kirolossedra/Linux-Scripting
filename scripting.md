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
