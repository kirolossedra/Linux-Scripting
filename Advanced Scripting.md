# Exercise 1 - Using Conditional Statements and Logical Operators

In this exercise, you will create a simple Bash script that uses conditional statements to respond to user input.

## 1.1 Create a New Bash Script

### Step 1: Create the Script File
Open your terminal and create a new script file named `response.sh`:

```bash
nano response.sh
```

### Step 2: Add the Shebang Line
At the top of the file, add the shebang line to specify the Bash interpreter:

```bash
#!/bin/bash
```

### Step 3: Save and Exit
Save your changes and exit the text editor (in `nano`, press `CTRL + O` to save and `CTRL + X` to exit).

### Step 4: Make the Script Executable
Run the following command to add execute permissions:

```bash
chmod +x response.sh
```

## 1.2 Query the User and Store Their Response

### Add User Query
Open the `response.sh` file again:

```bash
nano response.sh
```

### Prompt the User
Add the following lines to ask a binary "yes or no" question and store the response in a variable:

```bash
# Ask the user a binary "yes or no" question
echo -n "Do you like Bash scripting? (yes/no): "
read answer
```

## 1.3 Use a Conditional Block to Select a Response

### Implement Conditional Logic
Below the user query, add a conditional block to respond based on the user's answer:

```bash
# Use a conditional block to select a response
if [[ "$answer" == "yes" ]]; then
    echo "That's great to hear! Bash scripting is powerful."
elif [[ "$answer" == "no" ]]; then
    echo "That's okay! It’s not for everyone."
else
    echo "Please answer with 'yes' or 'no'."
fi
```

### Complete Script
Your complete `response.sh` script should look like this:

```bash
#!/bin/bash

# Ask the user a binary "yes or no" question
echo -n "Do you like Bash scripting? (yes/no): "
read answer

# Use a conditional block to select a response
if [[ "$answer" == "yes" ]]; then
    echo "That's great to hear! Bash scripting is powerful."
elif [[ "$answer" == "no" ]]; then
    echo "That's okay! It’s not for everyone."
else
    echo "Please answer with 'yes' or 'no'."
fi
```

### Save and Exit
Save your changes and exit the text editor.

### Execute the Script
Run the script using:

```bash
./response.sh
```

### Input Your Response
When prompted, enter your answer (yes or no) to see the corresponding message. If you provide any other input, the script will prompt you to answer with 'yes' or 'no'.

Congratulations! You have successfully created a Bash script that uses conditional statements and handles user input.




# Exercise 2 - Performing Basic Mathematical Calculations and Numerical Logical Comparisons

In this exercise, you will create a Bash script that performs arithmetic calculations on two integers provided by the user and evaluates the results.

## 2.1 Create a Bash Script

### Step 1: Create the Script File
Open your terminal and create a new script file named `calc.sh`:

```bash
nano calc.sh
```

### Step 2: Add the Shebang Line
At the top of the file, add the shebang line to specify the Bash interpreter:

```bash
#!/bin/bash
```

### Step 3: Prompt for User Input
Add code to prompt the user for two integers and store them:

```bash
# Prompt the user for two integers
echo -n "Enter the first integer: "
read first_num
echo -n "Enter the second integer: "
read second_num
```

### Step 4: Perform Calculations
Add code to calculate and print the sum and product of the two integers:

```bash
# Calculate the sum and product
sum=$((first_num + second_num))
product=$((first_num * second_num))

# Print the results
echo "Sum: $sum"
echo "Product: $product"
```

### Complete Script for 2.1
Your script should now look like this:

```bash
#!/bin/bash

# Prompt the user for two integers
echo -n "Enter the first integer: "
read first_num
echo -n "Enter the second integer: "
read second_num

# Calculate the sum and product
sum=$((first_num + second_num))
product=$((first_num * second_num))

# Print the results
echo "Sum: $sum"
echo "Product: $product"
```

### Step 5: Save and Exit
Save your changes and exit the text editor.

### Step 6: Make the Script Executable
Run the following command to add execute permissions:

```bash
chmod +x calc.sh
```

## 2.2 Add Logic to Your Script

### Step 1: Compare Sum and Product
Open the `calc.sh` file again:

```bash
nano calc.sh
```

### Step 2: Implement Conditional Logic
Add logic to compare the sum and product and display an appropriate message:

```bash
# Compare sum and product
if [[ $sum -gt $product ]]; then
    echo "The sum is greater than the product."
elif [[ $sum -lt $product ]]; then
    echo "The sum is less than the product."
else
    echo "The sum is equal to the product."
fi
```

### Complete Script for 2.2
Your final `calc.sh` script should look like this:

```bash
#!/bin/bash

# Prompt the user for two integers
echo -n "Enter the first integer: "
read first_num
echo -n "Enter the second integer: "
read second_num

# Calculate the sum and product
sum=$((first_num + second_num))
product=$((first_num * second_num))

# Print the results
echo "Sum: $sum"
echo "Product: $product"

# Compare sum and product
if [[ $sum -gt $product ]]; then
    echo "The sum is greater than the product."
elif [[ $sum -lt $product ]]; then
    echo "The sum is less than the product."
else
    echo "The sum is equal to the product."
fi
```

### Step 3: Save and Exit
Save your changes and exit the text editor.

### Step 4: Execute the Script
Run the script using:

```bash
./calc.sh
```

### Input Your Integers
When prompted, enter two integers. The script will display their sum and product, along with a comparison of the two results.

Congratulations! You have successfully created a Bash script that performs basic arithmetic calculations and logical comparisons.





# Exercise 3 - Using Arrays for Storing and Accessing Data Within For Loops

In this exercise, you will create a report from a CSV dataset, extracting columns into arrays, creating a new column, and saving the results as a new CSV file.

## 3.1 Download a CSV File

### Step 1: Download the CSV File
Open your terminal and run the following command to download the CSV file:

```bash
wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/M3/L2/arrays_table.csv
```

## 3.2 Display the CSV File

### Step 2: View the Contents
To understand the structure of the CSV file, you can display its contents using:

```bash
cat arrays_table.csv
```

## 3.3 Create a Bash Script that Parses Table Columns into 3 Arrays

### Step 1: Create the Script File
Create a new Bash script named `process_csv.sh`:

```bash
nano process_csv.sh
```

### Step 2: Add the Shebang Line
At the top of the file, add the shebang line:

```bash
#!/bin/bash
```

### Step 3: Read the CSV File and Parse Columns
Add the following code to read the CSV file and store the columns in arrays:

```bash
# Read the CSV file
input_file="arrays_table.csv"

# Initialize arrays
declare -a column1
declare -a column2
declare -a column3

# Read the file line by line
while IFS=, read -r col1 col2 col3; do
    column1+=("$col1")
    column2+=("$col2")
    column3+=("$col3")
done < <(tail -n +2 "$input_file")  # Skip the header line
```

## 3.4 Create a New Array as the Difference of the Third and Second Columns

### Step 1: Initialize a New Array
Add logic to create a new array for the differences:

```bash
# Create a new array for the differences
declare -a differences
differences=("Difference")  # Initialize with a header

# Calculate the differences
for i in "${!column2[@]}"; do
    diff=$((column3[i] - column2[i]))
    differences+=("$diff")
done
```

## 3.5 Create a Report by Combining Your New Column with the Source Table

### Step 1: Save the Combined Data as a New CSV File
Add the following code to create a report and save it as a CSV file:

```bash
# Create a new CSV report
output_file="report.csv"
{
    echo "Column1,Column2,Column3,Difference"  # Header
    for i in "${!column1[@]}"; do
        echo "${column1[i]},${column2[i]},${column3[i]},${differences[i + 1]}"
    done
} > "$output_file"

echo "Report saved as $output_file"
```

### Complete Script
Your complete `process_csv.sh` script should look like this:

```bash
#!/bin/bash

# Read the CSV file
input_file="arrays_table.csv"

# Initialize arrays
declare -a column1
declare -a column2
declare -a column3

# Read the file line by line
while IFS=, read -r col1 col2 col3; do
    column1+=("$col1")
    column2+=("$col2")
    column3+=("$col3")
done < <(tail -n +2 "$input_file")  # Skip the header line

# Create a new array for the differences
declare -a differences
differences=("Difference")  # Initialize with a header

# Calculate the differences
for i in "${!column2[@]}"; do
    diff=$((column3[i] - column2[i]))
    differences+=("$diff")
done

# Create a new CSV report
output_file="report.csv"
{
    echo "Column1,Column2,Column3,Difference"  # Header
    for i in "${!column1[@]}"; do
        echo "${column1[i]},${column2[i]},${column3[i]},${differences[i + 1]}"
    done
} > "$output_file"

echo "Report saved as $output_file"
```

### Step 2: Save and Exit
Save your changes and exit the text editor.

### Step 3: Make the Script Executable
Run the following command to make the script executable:

```bash
chmod +x process_csv.sh
```

### Step 4: Execute the Script
Run the script using:

```bash
./process_csv.sh
```

### Step 5: Validate Your Results
Check the contents of the newly created report CSV file:

```bash
cat report.csv
```

Congratulations! You have successfully created a Bash script that processes a CSV file, performs calculations, and generates a new report.
