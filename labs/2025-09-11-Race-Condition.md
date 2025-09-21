# Lab Title: Race Condition – TryHackMe
- Date: 2025-09-18

## Target
- TryHackMe Race Condition Lab
- Tested using local web application in lab environment

## Commands / Steps 
- Intercepted POST request for fund transfer using Burp Suite Proxy
- Sent intercepted request to Repeater
- Duplicated the request 20 times to exploit the race condition
- URl: Target IP:PORT
## Results
- Multiple fund transfers processed before backend updated balances
- Flag successfully captured

## Screenshots
- ![Task 1# output](../Screenshots/2025-09-18-Bank-Web-App.png)
- ![Task #2 output](../Screenshots/2025-09-18-Burpsuite.png)


## What I Learned
- Race condition occurs when multiple requests modify a resource simultaneously without proper locking
- Mitigation: Implement transaction locking or atomic operations in backend to prevent duplicates
