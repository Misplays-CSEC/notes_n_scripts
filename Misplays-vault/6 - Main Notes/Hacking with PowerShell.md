---
date: 2025-05-07 15:27
tags:
  - Powershell
author: Tryhackme
source:
---

# Source Notes

## Metadata

- **Date/Time**: 2025-05-07 15:27
- **Author**:  Tryhackme
- **Source**: https://tryhackme.com/room/powershell
- **Tags**: [[Powershell]]

---
## What is Powershell

Powershell is the Windows Scripting Language and shell environment built using the .NET framework.

This also allows Powershell to execute .NET functions directly from its shell. Most Powershell commands, called _cmdlets,_ are written in .NET. Unlike other scripting languages and shell environments, the output of these _cmdlets_ are objects - making Powershell somewhat object-oriented.

This also means that running cmdlets allows you to perform actions on the output object (which makes it convenient to pass output from one _cmdlet_ to another). The normal format of a _cmdlet_ is represented using **Verb-Noun**; for example, the _cmdlet_ to list commands is called `Get-Command`

Common verbs to use include:

- Get
- Start
- Stop 
- Read
- Write
- New
- Out

---
## Powershell Commands

**#1** What is the command to get help about a particular cmdlet(without any parameters)?

GET-HELP

**#1** What is the location of the file “interesting-file.txt”

Get-ChildItem -Path C:\ -Include *interesting-file.txt* -File -Recurse -ErrorAction SilentlyContinue

**#2** Specify the contents of this file

Get-Content "C:\Program Files\interesting-file.txt.txt"

**3** How many cmdlets are installed on the system(only cmdlets, not functions and aliases)?

Get-Command | Where-Object -Parameter CommandType -eq Cmdlet | measure

**#4** Get the MD5 hash of interesting-file.txt

Get-FileHash -Path "C:\Program Files\interesting-file.txt.txt" -Algorithm MD5

**#5** What is the command to get the current working directory?

Get-Location

**#6** Does the path “C:\Users\Administrator\Documents\Passwords” Exist(Y/N)?

Get-Location -Path "C:\Users\Administrator\Documents\Passwords"

**#7** What command would you use to make a request to a web server?

Invoke-WebRequest

**#8** Base64 decode the file b64.txt on Windows.

Get-ChildItem -Path C:/ -Include b64.txt -Recurse -File

certutil -decode "C:\Users\Administrator\Desktop\b64.txt" decode.txt

Get-Content .\decode.txt

**#1** How many users are there on the machine?

Get-LocalUser

**#2** Which local user does this SID(S-1–5–21–1394777289–3961777894–1791813945–501) belong to?

Get-LocalUser -SID "S-1-5-21-1394777289-3961777894-1791813945-501"

**#3** How many users have their password required values set to False?

Get-LocalUser | Where-Object -Property PasswordRequired -Match false

**#4** How many local groups exist?

Get-LocalGroup | measure

**#5** What command did you use to get the IP address info?

Get-NetIPAddress

**#6** How many ports are listed as listening?

GEt-NetTCPConnection | Where-Object -Property State -Match Listen | measure

**#7** What is the remote address of the local port listening on port 445?

GEt-NetTCPConnection | Where-Object -Property State -Match Listen

**#8** How many patches have been applied?

Get-Hotfix | measure

**#9** When was the patch with ID KB4023834 installed?

Get-Hotfix -Id KB4023834

**#10** Find the contents of a backup file.

Get-ChildItem -Path C:\ -Include *.bak* -File -Recurse -ErrorAction SilentlyContinueGet-Content "C:\Program Files (x86)\Internet Explorer\passwords.bak.txt"

**#11** Search for all files containing API_KEY

Get-ChildItem C:\* -Recurse | Select-String -pattern API_KEY

**#12** What command do you do to list all the running processes?

Get-Process

**#13** What is the path of the scheduled task called new-sched-task?

Get-ScheduleTask -TaskName new-sched-task

**#14**Who is the owner of the C:\

Get-Acl c:/


