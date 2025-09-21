# Lab Title: Intro to XSS – Blind XSS with Session Hijacking
Date: 2025-09-11

## Target
- TryHackMe – Intro to Cross-Site Scripting (Acme I.T. Support Webapp)

## Commands / Steps 
- Created a new user account and logged into the Acme I.T. Support Webapp.
- Started a netcat listener to wait for any incoming callback from the Blind XSS payload: nc -nlvp 9001
- Submitted a support ticket containing a crafted Blind XSS payload in the message field.
Payload was designed to exfiltrate the victim’s session cookie once the admin/staff viewed the ticket.
- Waited for the payload to be triggered when the staff opened the ticket in their panel.
- The payload executed and sent back a Base64-encoded value containing the stolen staff session cookie.
- Decoded the Base64 value using base64decode.org to reveal the staff-session details.

## Results
- Successfully exploited Blind XSS to execute JavaScript in the victim’s browser.
- Listener (nc -nlvp 9001) confirmed the incoming connection with the Base64-encoded cookie.
- Decoded the stolen staff session cookie, proving session hijacking was possible.

## Screenshots
- ![Netcat Listener](../Screenshots/2025-09-11-xss-blind-listener.png)  
- ![Acme Ticket Payload Submission](../Screenshots/2025-09-11-xss-blind-ticket.png)  
- ![Decoded Session Cookie](../Screenshots/2025-09-11-xss-blind-decoded.png)

## What I Learned
- XSS allows attackers to inject malicious scripts into web applications.
- Blind XSS is powerful because the attacker doesn’t see the effect immediately — it executes when another user (like an admin) views the malicious input.
- By combining XSS with a listener, attackers can exfiltrate cookies or sensitive data in real time.
- Cookies and session tokens are prime targets for XSS attacks.
    Defense strategies:
  * Sanitize and escape user input.
  * Use HTTP Only cookies to prevent JavaScript from accessing session tokens.
  * Implement Content Security Policy (CSP) to reduce XSS risks.
