Sure! Here’s a structured approach to completing the exercises you've provided for initializing a weather report log, writing a bash script, and scheduling it to run automatically.

---

## Exercise 1 - Initialize Your Weather Report Log File

### 1.1 Create a Text File Called `rx_poc.log`

To create the log file, open your terminal and run:

```bash
touch rx_poc.log
```

### 1.2 Add a Header to Your Weather Report

You can add a header with tab-delimited column names using either of these methods:

Using a variable:

```bash
header=$(echo -e "year\tmonth\tday\thour\tobs_tmp\tfc_temp")
echo $header > rx_poc.log
```

Or directly:

```bash
echo -e "year\tmonth\tday\thour\tobs_tmp\tfc_temp" > rx_poc.log
```

---

## Exercise 2 - Write a Bash Script

### 2.1 Create a Bash Script File

Create the script file and make it executable:

```bash
touch rx_poc.sh
chmod +x rx_poc.sh
```

### 2.2 Download Today’s Weather Report

#### 2.2.1 Create the Filename

You can create a filename with today’s date:

```bash
today=$(date +%Y%m%d)
weather_report="raw_data_$today"
```

#### 2.2.2 Download the Weather Report

Use `curl` to download the weather report for Casablanca:

```bash
city="Casablanca"
curl "wttr.in/$city" --output "$weather_report"
```

### 2.3 Extract Required Data

You will extract temperature data from the raw file.

#### 2.3.1 Extract Current Temperature

Extract the current temperature:

```bash
obs_tmp=$(grep -o '[0-9]\+°C' "$weather_report" | head -n 1 | tr -d '°C')
```

#### 2.3.2 Extract Tomorrow’s Temperature Forecast

Extract tomorrow's temperature forecast:

```bash
fc_temp=$(grep -o '[0-9]\+°C' "$weather_report" | head -n 2 | tail -n 1 | tr -d '°C')
```

### 2.4 Store Current Date and Time

Store the current date and time in variables:

```bash
hour=$(TZ='Morocco/Casablanca' date -u +%H)
day=$(TZ='Morocco/Casablanca' date -u +%d)
month=$(TZ='Morocco/Casablanca' date +%m)
year=$(TZ='Morocco/Casablanca' date +%Y)
```

### 2.5 Append Data to Your Log File

Create a tab-delimited record and append it to the log:

```bash
record=$(echo -e "$year\t$month\t$day\t$hour\t$obs_tmp\t$fc_temp")
echo -e "$record" >> rx_poc.log
```

---

## Exercise 3 - Schedule Your Bash Script

### 3.1 Determine the Time to Run Your Script

To run your script at noon in Casablanca, determine the time difference from UTC. For example, if your local time is UTC+5, you would run your script at 8 AM.

### 3.2 Create a Cron Job

Edit the crontab:

```bash
crontab -e
```

Add the following line:

```bash
0 8 * * * /path/to/rx_poc.sh
```

Make sure to replace `/path/to/` with the actual path to your script.

---

Congratulations on completing the project! You’ve set up a system to log daily weather data automatically. If you need any further assistance or clarifications, feel free to ask!
