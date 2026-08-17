 # Day 4 - Linux Shell Scripting

## Topics Covered
- Shell Scripting Basics
- Variables
- echo command
- if-else condition
- CPU Utilization
- Memory Utilization
- Disk Utilization
- Running Processes
- File Permission Check

## Commands Practiced
- top
- free
- df
- ps
- grep
- awk
- cut
README.md
# 15 August - Shell Scripting Practice

## Task
Created a basic Linux Health Check Script.

15-Aug-2026/
│── README.md
│── health.sh
│── notes.md
│── commands.txt
health.sh
CPU Utilization
Memory Utilization
Disk Utilization
Running Processes
Permission Check
Alert Condition (40%)
commands.txt

touch
nano
chmod +x
bash
top
free
df -h
ps -e
wc -l
grep
awk
cut
echo
if
notes.md
Day 4 - Linux Shell Scripting

## Topics Covered
- Shell Scripting Basics
- Variables
- echo command
- if-else condition
- CPU Utilization
- Memory Utilization
- Disk Utilization
- Running Processes
- File Permission Check

## Commands Practiced
- top
- free
- df
- ps
- grep
- awk
- cut
README.md
# 15 August - Shell Scripting Practice



#Task
### Features
- CPU Usage Check
- Memory Usage Check
- Disk Usage Check
- Running Processes Count
- File Permission Check
- Alert when Memory Usage > 40%

  
echo "===== System Health Check ====="

# CPU Usage
cpu=$(top -bn1 | grep "Cpu(s)" | cut -d "," -f1)
echo "CPU Usage : $cpu"

# Memory Usage
memory=$(free -m | grep Mem)
echo "Memory : $memory"

# Disk Usage
disk=$(df -h / | tail -1 | awk '{print $5}')
echo "Disk Usage : $disk"

# Running Processes
process=$(ps -e | wc -l)
echo "Running Processes : $process"

# Permission Check
if [ -r "/etc/passwd" ]
then
    echo "Read Permission : Yes"
else
    echo "Read Permission : No"
fi

# Alert Condition
mem=$(free | awk '/Mem:/ {print int($3/$2*100)}')

if [ "$mem" -gt 40 ]
then
    echo "Alert! Memory usage is above 40%"
else
    echo "Memory usage is normal."
fi

echo "===== Health Check Complete ====="


## Technologies
- Linux
- Bash
- Shell Scripting
Commit Message
git add .
git commit -m "Add Linux health check shell script and practice notes"
git push origin main

### Features
- CPU Usage Check
- Memory Usage Check
- Disk Usage Check
- Running Processes Count
- File Permission Check
- Alert when Memory Usage > 40%

## Technologies
- Linux
- Bash
- Shell Scripting
Commit Message
git add .
git commit -m "Add Linux health check shell script and practice notes"
git push origin main

### Features
- CPU Usage Check
- Memory Usage Check
- Disk Usage Check
- Running Processes Count
- File Permission Check
- Alert when Memory Usage > 40%

## Technologies
- Linux
- Bash
- Shell Scripting
Commit Message
git add .
git commit -m "Add Linux health check shell script and practice notes"
git push origin main
