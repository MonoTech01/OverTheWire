# Windows Forensics: Fundamental Level Guide for System Administrators

## Connection
via RDP - Remote Desktop Connnection if you are not in the target machine yet!

Username: Administrator
Password: letmein123!

Search RDP in the search bar - fill "Computer" section with IP address -> fill in username and password

## Check computer's info
Powershell
Command: systeminfo
### Contents: host name, os version, manufacturer, processor, time zone, ...

## Check user account
Powershell
Command: net user -> check how many and who users are
Command: net user [specific name] -> more info like last login

## What IP does the system connect to when it first starts
Search "Regedit" for Registry Editor in search bar.

HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > Run

When you are in "Run" location, pls check the ip address of UpdateSvc = reveals the IP address that the remote machine connects to when it starts.

## What two accounts had administrative privileges (other than the Administrator user)?
### Command: 
    net localgroup administrators

## Whats the name of the scheduled task that is malicous? What file was the task trying to run daily + What port did this file listen locally for?

### Command:  
    Get-ScheduledTask
### Command:  
    $task = Get-ScheduledTask | Where TaskName -EQ “[file's name]”
    $task.actions

## When did [a user] last logon?
### Command: 
    net user [a username]
    net user [a username] | findstr "Last" #another way
    
