Here's a structured guide to help you navigate through the exercises on viewing and manipulating file contents using various commands in a Unix-like environment.

---

## Exercise 1 - Viewing File Contents

### 1.1 Viewing File Content with `cat`

To view the contents of `entrypoint.sh`, use:

```bash
cat entrypoint.sh
```

### 1.2 Viewing File Content with `more`

For a paginated view, use `more`:

```bash
more entrypoint.sh
```
- Press the spacebar to see more content.
- Type `q` to quit.

### 1.3 Scrolling Through File Content with `less`

Use `less` for more flexibility:

```bash
less entrypoint.sh
```
- Navigate using the arrow keys and `Page Up`/`Page Down`.
- Type `q` to exit.

---

## Exercise 2 - Viewing Text File Contents

### 2.1 Display the First N Lines of a File with `head`

To display the first 10 lines:

```bash
head usdoi.txt
```

To display the first 3 lines:

```bash
head -3 usdoi.txt
```

### 2.2 Display the Last N Lines of a File with `tail`

To display the last 10 lines:

```bash
tail usdoi.txt
```

To display the last 2 lines:

```bash
tail -2 usdoi.txt
```

---

## Exercise 3 - Getting Basic Text File Stats

### 3.1 Count Lines, Words, or Characters with `wc`

To get the count of lines, words, and characters:

```bash
wc usdoi.txt
```

To get just the line count:

```bash
wc -l usdoi.txt
```

To count words:

```bash
wc -w usdoi.txt
```

To count characters:

```bash
wc -c usdoi.txt
```

---

## Exercise 4 - Basic Text Wrangling

### 4.1 Sort and Display Lines with `sort`

To sort lines alphanumerically:

```bash
sort usdoi.txt
```

To sort in reverse order:

```bash
sort -r usdoi.txt
```

### 4.2 Drop Consecutive Duplicated Lines with `uniq`

First, download the file:

```bash
wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/module%201/zoo.txt
```

To view contents with duplicates removed:

```bash
uniq zoo.txt
```

---

## Exercise 5 - Extracting Lines and Fields

### 5.1 Extract Lines Matching a Criterion with `grep`

To find lines containing "people":

```bash
grep people usdoi.txt
```

### 5.2 Extract Fields from Lines with `cut`

To view the first two characters of each line:

```bash
cut -c -2 zoo.txt
```

To extract the second field from a CSV:

```bash
cut -d "," -f2 names_and_numbers.csv
```

---

## Exercise 6 - Merging Lines as Fields

### 6.1 Merge Text Files Line-by-Line with `paste`

Download the file:

```bash
wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/module%201/zoo_ages.txt
```

To merge files:

```bash
paste zoo.txt zoo_ages.txt
```

To change the delimiter to a comma:

```bash
paste -d "," zoo.txt zoo_ages.txt
```

---

## Practice Exercises

1. **Display the number of lines in `/etc/passwd`:**
   ```bash
   wc -l /etc/passwd
   ```

2. **Display lines containing "not installed" in `/var/log/bootstrap.log`:**
   ```bash
   grep "not installed" /var/log/bootstrap.log
   ```

3. **Find all websites with "org" in `top-sites.txt`:**
   ```bash
   wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0250EN-SkillsNetwork/labs/Bash%20Scripting/top-sites.txt
   grep org top-sites.txt
   ```

4. **Print the first seven lines of `top-sites.txt`:**
   ```bash
   head -n 7 top-sites.txt
   ```

5. **Print the last seven lines of `top-sites.txt`:**
   ```bash
   tail -n 7 top-sites.txt
   ```

6. **Print the first three characters of each line from `top-sites.txt`:**
   ```bash
   cut -c -3 top-sites.txt
   ```

7. **Extract and view only the names from `names_and_numbers.csv`:**
   ```bash
   cd /home/project
   cut -d "," -f 1 names_and_numbers.csv
   ```

---

This guide should help you understand the various commands and their uses in file manipulation and exploration. If you have any questions or need further clarification on any part, feel free to ask!
