Here's a structured guide for viewing network configuration information, testing connectivity, and downloading data from servers using various commands in a Unix-like environment.

---

## Exercise 1 - View Configuration Info About Your Network

### 1.1 Display Your System's Hostname and IP Address

**To view the current hostname:**

```bash
hostname
```

**To view the IP address:**

```bash
hostname -i
```

### 1.2 Display Network Interface Configuration

**To display the configuration of all network interfaces:**

```bash
ifconfig
```

**To display the configuration of a specific device (e.g., `eth0`):**

```bash
ifconfig eth0
```

---

## Exercise 2 - Test Network Connectivity

### 2.1 Test Connectivity to a Host

**To check if `www.google.com` is reachable:**

```bash
ping www.google.com
```

- **To limit the number of pings (e.g., 5 times):**

```bash
ping -c 5 www.google.com
```

---

## Exercise 3 - View or Download Data from a Server

### 3.1 Transfer Data from a Server Using `curl`

**To display the contents of a file at a URL:**

```bash
curl https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0250EN-SkillsNetwork/labs/Bash%20Scripting/usdoi.txt
```

**To save the file in your current directory:**

```bash
curl -O https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0250EN-SkillsNetwork/labs/Bash%20Scripting/usdoi.txt
```

### 3.2 Download File(s) from a URL Using `wget`

**To remove an existing file (if needed):**

```bash
rm usdoi.txt
```

**To download it again using `wget`:**

```bash
wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0250EN-SkillsNetwork/labs/Bash%20Scripting/usdoi.txt
```

---

## Practice Exercises

1. **Display your host's IP address:**

```bash
hostname -i
```

2. **Get connectivity stats on your connection to `www.google.com`:**

```bash
ping www.google.com
```

3. **View info about your ethernet adapter `eth0`:**

```bash
ifconfig eth0
```

4. **View the HTML code for `www.google.com's` landing page:**

```bash
curl www.google.com
```

5. **Download the HTML code for `www.google.com's` landing page:**

```bash
wget www.google.com
```

**Note:** `wget` saves the HTML code as `index.html`. Check with:

```bash
ls -l
```

---

This guide should help you understand how to manage and view network configurations, test connectivity, and handle data transfers in a Unix-like environment. If you have any questions or need further assistance, feel free to ask!
