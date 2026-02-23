# Shell Scripting – Basics

Shell scripting is used to automate repetitive tasks in Linux environments.

In DevOps, shell scripts are used for:

- Deployment automation
- System monitoring
- Backup scripts
- CI/CD tasks
- Server configuration

---

## What is a Shell?

A shell is a command-line interpreter that interacts with the operating system.

Common shells:

- bash
- sh
- zsh

In DevOps, bash is most commonly used.

---

## Shebang

Every shell script starts with:

#!/bin/bash

This tells the system which interpreter to use.

---

## Creating a Script

Create file:

touch script.sh

Give permission:

chmod +x script.sh

Run script:

./script.sh

---

## Variables

Define variable:

name="Abhishek"

Access variable:

echo $name

Important: No space around =

---

## User Input

read variable_name

Example:

echo "Enter your name:"
read name
echo "Hello $name"

---

## Conditional Statements

if condition
then
  commands
fi

Example:

if [ $a -gt $b ]
then
  echo "A is greater"
fi

Comparison operators:

-eq (equal)  
-ne (not equal)  
-gt (greater than)  
-lt (less than)  

---

## Loops

### For Loop

for i in 1 2 3
do
  echo $i
done

### While Loop

while [ condition ]
do
  commands
done

---

## Comments

Single line comment:

# This is a comment

---

## Exit Status

Every command returns exit status:

0 → Success  
Non-zero → Error  

Check exit status:

echo $?

Important for automation and CI/CD.

---

## Why Shell Scripting is Important in DevOps

- Automates repetitive tasks
- Reduces manual errors
- Used in CI/CD pipelines
- Used for deployment scripts
- Used for monitoring scripts

Shell scripting is one of the core skills of a DevOps Engineer.
