---
title: Batch - creating directory with timestamp as dir name.
date: 2024-01-10 21:07:00 +100
categories: [batch]
tags: [batch]
---

# Batch script pattern. 


```batch
::CREATE TIMESTAMP
@echo off
for /f "tokens=2 delims==" %%a in ('wmic OS Get localdatetime /value') do set "dt=%%a"
set "YY=%dt:~2,2%" & set "YYYY=%dt:~0,4%" & set "MM=%dt:~4,2%" & set "DD=%dt:~6,2%"
set "HH=%dt:~8,2%" & set "Min=%dt:~10,2%" & set "Sec=%dt:~12,2%"
set "fullstamp=%YYYY%-%MM%-%DD%_%HH%%Min%-%Sec%"

::CREATE LOGS DIR 
For %%A in (mkdir .\LOGS_%fullstamp%) do (
	Set logs_dir=%%~nxA
)
echo %logs_dir%
```
Script output:
![localImage](/assets/images/logs_dir_01142024.PNG)
