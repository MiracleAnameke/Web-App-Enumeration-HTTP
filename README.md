# Web Security
## Web App Enumeration & HTTP

### Lab Requirements
- VM Snapshots from Lab 04
- Internet connectivity & VMware Workstation version 15.5.7 or above
- Ensure that you can browse from Kali’s Firefox to FOLusername-uws/mutillidae

### Lab Tasks and Screenshots

### Part 01: Capture HTTP Requests and Responses
**Task**: Understand and capture various HTTP requests and responses using Burp Suite.
- **Slide 01**: HTTP Request showing the User-Agent. Highlight the User-Agent.
  <img src="https://i.imgur.com/u6ZCqrv.png" height="400px" width="auto" alt="HTTP Request User-Agent"/>
  
- **Slide 02**: HTTP Response showing a status code of 404. Highlight the status code.
  <img src="https://i.imgur.com/04tQON2.png" height="400px" width="auto" alt="HTTP Response 404"/>

### Part 02: Take Over a Session
**Task**: Use Burp Suite to manipulate session cookies and take over another user's session.
- **Steps**:
    1. Create two new users in Mutillidae: FOLusername-01 and FOLusername-02.
    2. Login as FOLusername-01 and capture the Set-Cookie information from Burp Suite.
    3. Use this cookie information to log in as FOLusername-02 but navigate as FOLusername-01.
- **Slide 03**: Highlight the Set-Cookie field from the captured request.
  <img src="https://i.imgur.com/0QAJYh0.png" height="400px" width="auto" alt="Set-Cookie Highlight"/>
  
- **Slides 04 & 05**: Show the original and edited requests that lead to session takeover.
  <img src="https://i.imgur.com/pIqDBVz.png" height="400px" width="auto" alt="Original Request for Session Takeover"/>
  <img src="https://i.imgur.com/rwR1BjK.png" height="400px" width="auto" alt="Edited Request for Session Takeover"/>
  
- **Slide 06**: Capture the edited request for Admin Login.
  <img src="https://i.imgur.com/J60lLEB.png" height="400px" width="auto" alt="Admin Login Attempt"/>

### Part 03: Change the User-Agent HTTP Header in Firefox
**Task**: Modify the User-Agent header in Firefox to execute JavaScript or display custom messages.
- **Steps**:
    1. Reset the DB in Mutillidae and navigate to a new page while intercepting the packets.
    2. Modify the User-Agent Header in the captured HTTP request packet to reflect custom JavaScript.
    3. Observe the result of the modification, such as an alert box or changed user-agent information in Mutillidae's footer.
- **Slide 07**: Show the Original Request packet with the custom User-Agent and resulting alert box or page change.

<img src="https://i.imgur.com/c8hKTb7.png" height="400px" width="auto" alt="User-Agent Header Modification"/>
<img src="https://i.imgur.com/IjgRI0F.png" height="400px" width="auto" alt="User-Agent Header Modification"/>

### Part 04: Burp Suite Intruder
**Task**: Use Burp Suite's Intruder feature to test for weak passwords or perform automated attacks.
- **Steps**:
    1. Create a new account in Mutillidae and capture the login attempt using Burp Suite.
    2. Use Burp Suite Intruder to automate login attempts with a list of potential passwords.
    3. Look for a successful login indicated by a 302 redirect or other server response.
- **Slide 08**: Show the raw tab used in the request that received the 302 status code indicating a successful login.

<img src="https://i.imgur.com/smDOPTr.png" height="400px" width="auto" alt="Burp Suite Intruder Attack"/>

**Conclusion**: This lab provides a hands-on approach to understanding web application traffic, session management, and the power of tools like Burp Suite for enumeration and testing. By completing these tasks, students gain valuable insight into HTTP mechanisms and security testing techniques.
