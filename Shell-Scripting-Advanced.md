# Shell Scripting – Advanced

Advanced shell scripting is used for complex automation tasks in DevOps environments.

It allows building reusable scripts, handling errors, and managing system operations efficiently.

---

## Functions

Functions help reuse code.

Example:

greet() {
  echo "Hello, $1"
}

greet Abhishek

$1 represents first argument.

---

## Script Arguments

Access arguments:

$1 → First argument  
$2 → Second argument  
$# → Number of arguments  
$@ → All arguments  

Example:

echo "First argument is $1"

Run:

./script.sh test

---

## Case Statement

Used for multiple conditions.

case $variable in
  1)
    echo "Option 1"
    ;;
  2)
    echo "Option 2"
    ;;
  *)
    echo "Invalid option"
    ;;
esac

---

## Input Validation

Check if file exists:

if [ -f filename ]
then
  echo "File exists"
fi

Common checks:

-f → File exists  
-d → Directory exists  
-z → String is empty  

---

## Error Handling

Check exit status:

if [ $? -ne 0 ]
then
  echo "Command failed"
fi

Used heavily in CI/CD automation.

---

## Redirecting Output

Overwrite file:

command > file.txt

Append output:

command >> file.txt

Error redirection:

command 2> error.txt

Redirect both:

command > output.txt 2>&1

---

## Pipes

Pass output of one command to another:

ls -l | grep ".sh"

Pipes are widely used in automation scripts.

---

## Cron Jobs (Automation Scheduling)

Edit crontab:

crontab -e

Format:

Minute Hour Day Month Weekday Command

Example:

0 2 * * * /home/user/backup.sh

Runs daily at 2 AM.

---

## Log Monitoring Example Script

#!/bin/bash

LOGFILE="/var/log/syslog"

if grep "error" $LOGFILE
then
  echo "Errors found"
else
  echo "No errors"
fi

---

## Why Shell Advanced is Important in DevOps

- Automating deployments
- Monitoring systems
- Scheduling backups
- Writing CI/CD scripts
- Handling production tasks

Advanced scripting separates beginners from professional DevOps engineers.
