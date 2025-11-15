
---
# phishing campaign
A phishing campaign in a corporate context is a simulated attack designed to mimic real-world phishing attempts, where employees receive deceptive emails or messages that try to trick them into revealing sensitive information such as passwords, financial data, or internal credentials. Red teamers carry out these campaigns to assess the human layer of security, identify weaknesses in employee awareness, and evaluate how well security policies are enforced.

For example, a red team at a company like Deloitte might send employees an email appearing to be from the IT department, requesting password resets due to a "security update." Some employees may click the link and enter credentials on a fake portal. The red team then analyzes which departments were most susceptible, measures response times to suspicious emails, and provides actionable recommendations for training, technical controls, or policy adjustments to strengthen the organization against real phishing attacks.

> In a red team scenario, if an employee clicks the link or submits credentials, the red team records the action as a security lapse. They do not steal real data but use the incident to highlight vulnerabilities in human behavior. The employee may receive immediate feedback or be enrolled in targeted security training to prevent future mistakes.

When employees receive a suspicious email, they should **not click links or provide information**, **report it to the security team**, **delete it**, and **follow company guidance**. This prevents data compromise and helps improve overall security awareness.

```r
[Security Team]  
      |  
      v  
[GoPhish Server] -- Sends --> [Employee Emails]  
      |                           |  
      |                      Employee clicks link  
      v                           |  
[Landing Page (Fake login)] <-- Collects response  
      |  
      v  
[Reports & Metrics for Security Team]
```

---
# Requirements 
Red teamers use specialized phishing simulation tools to carry out campaigns safely and effectively. Common tools include **`GoPhish`**, **`King Phisher`**, **`PhishMe`**, and **`LUCY`**, which allow teams to craft realistic phishing emails, track clicks, and analyze employee responses without compromising real data.

For example, using `GoPhish`, a red team can send a simulated email with a fake login page, monitor who interacts with it, and generate reports on which employees or departments are most vulnerable, helping the organization strengthen training and technical defenses.

---
# Setup 

Link : https://github.com/gophish/gophish/releases/

<img width="1807" height="725" alt="Pasted image 20250811110919" src="https://github.com/user-attachments/assets/67ea7c5b-9847-4dab-84a6-18dc9c09c543" />


1. Download for windows 
2. Unzip the file

<img width="1226" height="764" alt="Pasted image 20250811110957" src="https://github.com/user-attachments/assets/be2e3b54-9feb-4266-bbe1-f8315451d7c5" />



4. Run `gophish.exe`

<img width="1726" height="923" alt="Pasted image 20250811111034" src="https://github.com/user-attachments/assets/d2471b0e-baa7-441e-81b2-f08cbd3d7c76" />

7. It will launch the server at `https://127.0.0.1:3333`

<img width="1913" height="1074" alt="Pasted image 20250811111228" src="https://github.com/user-attachments/assets/27369e9c-9b19-4bd2-a9fe-2b0ab88d611c" />


> You will get Creds to login in terminal. 

<img width="1034" height="282" alt="Pasted image 20250811112319" src="https://github.com/user-attachments/assets/7c7c7ba7-c231-4de1-8179-b0e620f31bf7" />

5. after authentication you will be redirected to `set new password page`

<img width="1914" height="1068" alt="Pasted image 20250811112715" src="https://github.com/user-attachments/assets/9eeb6089-2f23-4c70-8e35-5ec57faa4507" />


6. Here we are on our `dashboard` of `gophish`

<img width="1913" height="1080" alt="Pasted image 20250811112953" src="https://github.com/user-attachments/assets/c0b5b49c-47da-405b-b755-87ed44b1c2a7" />

---
# Launching a phishing Campaign 

---
- `Sending Profiles ` In GoPhish, a sending profile is the **email account setup that the tool uses to send phishing emails**. It includes details like the email address, password, and server settings, so the emails come from a real-looking source and the campaign can track who opens or clicks them.

<img width="1919" height="687" alt="Pasted image 20250925175325" src="https://github.com/user-attachments/assets/a86afd35-33e4-4450-bfc7-6562dbaa3cfa" />


- **Name** – A label for the profile to identify it in campaigns.
- **From Address** – The email address that will appear as the sender.
- **SMTP Host** – The server address used to send emails (for example, smtp.gmail.com).
- **SMTP Port** – The port number for the server, usually` 587 for TLS` or `465 for SSL.`
- **Username** – The login name for the email account.
- **Password** – The password or app-specific password for the email account.
- **Use TLS/SSL** – Security options to encrypt the email transmission.

<img width="1327" height="999" alt="Pasted image 20250925175910" src="https://github.com/user-attachments/assets/054452b4-cdd7-47b3-9344-3f2cbd2567fc" />


> Note : You can head over to the Sections in `Google Account Management Section `  and search for `App Passwords`  and create new one to add in password section 

<img width="1757" height="961" alt="Pasted image 20250925180042" src="https://github.com/user-attachments/assets/d4d3dfd6-53c9-4330-822b-9f0558fea1bf" />


- After Setting up every thing try to send test mail to verify everything is working smoothly 

<img width="734" height="369" alt="Pasted image 20250925180320" src="https://github.com/user-attachments/assets/bcd2d365-dd38-4dd8-bd6d-ff22b06dcda8" />

<img width="1333" height="741" alt="Pasted image 20250925180348" src="https://github.com/user-attachments/assets/1b21d24e-f3ae-4792-8586-ee8d488e2980" />

> If successful then `save profile`

<img width="1586" height="476" alt="Pasted image 20250925180505" src="https://github.com/user-attachments/assets/05c91693-21a6-4a1c-9e39-ab47351a8dc2" />


---
- `Phishing Email Templates or PreText Mail` Phishing email templates, also called **pretext emails**, are pre-designed messages that mimic real communication to trick employees into taking an action, like clicking a link or entering credentials.
	- These templates usually follow a realistic scenario or story, such as an IT password reset, HR announcement, or invoice request, to make the email appear legitimate. In a red team campaign, these templates are customized with company branding, sender names, and relevant context so employees are more likely to interact, allowing the team to test human vulnerabilities safely.

<img width="1413" height="1060" alt="Pasted image 20250925181540" src="https://github.com/user-attachments/assets/8bd183a9-2973-4961-bd5d-69a406a88a64" />


```r
<p>Dear {{.FirstName}},</p>

<p>We are pleased to inform you that you have been shortlisted for the Deloitte Summer Internship Program 2025. Congratulations!</p>

<p>To confirm your participation and complete the onboarding process, please <a href="http://example.com/fake-onboarding">click here</a> and fill out the required details.</p>

<p>Please complete the form by <b>October 5, 2025</b> to secure your position.</p>

<p>Best Regards,<br>
Deloitte Recruitment Team</p>

```
<img width="821" height="486" alt="Pasted image 20250925181915" src="https://github.com/user-attachments/assets/5711deba-6280-48a3-9d84-67362f033db6" />

> Click on `Source` to render

<img width="1032" height="586" alt="Pasted image 20250925181936" src="https://github.com/user-attachments/assets/8997232e-5cd7-42ef-9f6c-783961366b88" />

> Save `Template`

<img width="1584" height="496" alt="Pasted image 20250925182122" src="https://github.com/user-attachments/assets/fd4cec9d-38fa-4ea6-93b7-507bb12fc7e8" />

---
- `Landing Page` : In GoPhish, the **landing page** is the webpage that the phishing email directs the recipient to. It is where the simulated attack collects interactions like clicks, submitted credentials, or form completions safely, without stealing real data.

```r
<html>
<head>
<title>Deloitte Internship Onboarding</title>
</head>
<body>
<h2>Welcome to Deloitte Summer Internship 2025</h2>
<p>Dear {{.FirstName}},</p>

<p>To confirm your internship position, please enter your login details below:</p>

<form action="{{.URL}}" method="POST">
    <label for="username">Email:</label><br>
    <input type="text" id="username" name="username" placeholder="your email"><br><br>
    <label for="password">Password:</label><br>
    <input type="password" id="password" name="password" placeholder="your password"><br><br>
    <input type="submit" value="Submit">
</form>

<p>Once submitted, you will receive further onboarding instructions.</p>

<p>Best Regards,<br>
Deloitte Recruitment Team</p>
</body>
</html>

```
<img width="1339" height="993" alt="Pasted image 20250925182357" src="https://github.com/user-attachments/assets/40edee5e-0ba5-4ae2-b5ad-8fe190e8dee1" />

<img width="1592" height="487" alt="Pasted image 20250925182543" src="https://github.com/user-attachments/assets/2ea12c8a-09c8-48a3-a317-e2f8abd3d096" />


---
- `Users & Groups` In GoPhish, the **Users & Groups** section is where you define and organize the people who will receive your phishing emails.

<img width="1580" height="328" alt="Pasted image 20250925182554" src="https://github.com/user-attachments/assets/071abefe-92ab-42eb-b447-e2c21a91bd3b" />


- Add details and save changes

<img width="1476" height="644" alt="Pasted image 20250925182742" src="https://github.com/user-attachments/assets/4070abfd-0bb6-4f59-ac92-099b3b1e40fa" />

<img width="1584" height="488" alt="Pasted image 20250925182817" src="https://github.com/user-attachments/assets/3fd8e075-0415-4e89-94bc-0d29d89f62c7" />

---

- `Launch Campaign` where you assemble template, sending profile, landing page and group, set URL and schedule, then launch. shows status and lets you monitor sends like dashboard of opens, clicks, submissions and timestamps with exportable logs. used for analysis and reporting.

<img width="1596" height="928" alt="Pasted image 20250925183005" src="https://github.com/user-attachments/assets/80784afb-174c-4353-9d3b-6000a6b760cc" />


> After Launching Campaign Targets will get Mails related to phishing like this 

<img width="1151" height="146" alt="Pasted image 20250925183131" src="https://github.com/user-attachments/assets/1dbb12b9-b39c-4eef-bc01-48255b339a2d" />

<img width="1404" height="856" alt="Pasted image 20250925183108" src="https://github.com/user-attachments/assets/37257cd3-e273-4bff-9ce1-dbe533f0982e" />

---
---
# Email Spoofing 

Email spoofing is when an attacker forges email sender fields so a message appears to come from a trusted source. motive is social engineering, credential theft, fraud or bypassing simple filters.

Link : https://emkei.cz/

---


