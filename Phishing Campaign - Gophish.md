
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
![[Pasted image 20250811110957.png]]

3. Run `gophish.exe`
![[Pasted image 20250811111034.png]]
4. It will launch the server at `https://127.0.0.1:3333`

![[Pasted image 20250811111228.png]]

> You will get Creds to login in terminal. 

![[Pasted image 20250811112319.png]]

5. after authentication you will be redirected to `set new password page`
![[Pasted image 20250811112715.png]]

6. Here we are on our `dashboard` of `gophish`
![[Pasted image 20250811112953.png]]

---
# Launching a phishing Campaign 

---
- `Sending Profiles ` In GoPhish, a sending profile is the **email account setup that the tool uses to send phishing emails**. It includes details like the email address, password, and server settings, so the emails come from a real-looking source and the campaign can track who opens or clicks them.
![[Pasted image 20250925175325.png]]

- **Name** – A label for the profile to identify it in campaigns.
- **From Address** – The email address that will appear as the sender.
- **SMTP Host** – The server address used to send emails (for example, smtp.gmail.com).
- **SMTP Port** – The port number for the server, usually` 587 for TLS` or `465 for SSL.`
- **Username** – The login name for the email account.
- **Password** – The password or app-specific password for the email account.
- **Use TLS/SSL** – Security options to encrypt the email transmission.

![[Pasted image 20250925175910.png]]

> Note : You can head over to the Sections in `Google Account Management Section `  and search for `App Passwords`  and create new one to add in password section 

![[Pasted image 20250925180042.png]]

- After Setting up every thing try to send test mail to verify everything is working smoothly 
![[Pasted image 20250925180320.png]]

![[Pasted image 20250925180348.png]]

> If successful then `save profile`

![[Pasted image 20250925180505.png]]

---
- `Phishing Email Templates or PreText Mail` Phishing email templates, also called **pretext emails**, are pre-designed messages that mimic real communication to trick employees into taking an action, like clicking a link or entering credentials.
	- These templates usually follow a realistic scenario or story, such as an IT password reset, HR announcement, or invoice request, to make the email appear legitimate. In a red team campaign, these templates are customized with company branding, sender names, and relevant context so employees are more likely to interact, allowing the team to test human vulnerabilities safely.
![[Pasted image 20250925181540.png]]

```r
<p>Dear {{.FirstName}},</p>

<p>We are pleased to inform you that you have been shortlisted for the Deloitte Summer Internship Program 2025. Congratulations!</p>

<p>To confirm your participation and complete the onboarding process, please <a href="http://example.com/fake-onboarding">click here</a> and fill out the required details.</p>

<p>Please complete the form by <b>October 5, 2025</b> to secure your position.</p>

<p>Best Regards,<br>
Deloitte Recruitment Team</p>

```

![[Pasted image 20250925181915.png]]

> Click on `Source` to render 

![[Pasted image 20250925181936.png]]

> Save `Template`

![[Pasted image 20250925182122.png]]

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

![[Pasted image 20250925182357.png]]

![[Pasted image 20250925182543.png]]

---
- `Users & Groups` In GoPhish, the **Users & Groups** section is where you define and organize the people who will receive your phishing emails.

![[Pasted image 20250925182554.png]]

- Add details and save changes
![[Pasted image 20250925182742.png]]

![[Pasted image 20250925182817.png]]

---

- `Launch Campaign` where you assemble template, sending profile, landing page and group, set URL and schedule, then launch. shows status and lets you monitor sends like dashboard of opens, clicks, submissions and timestamps with exportable logs. used for analysis and reporting.

![[Pasted image 20250925183005.png]]

> After Launching Campaign Targets will get Mails related to phishing like this 

![[Pasted image 20250925183131.png]]


![[Pasted image 20250925183108.png]]

---
---
# Email Spoofing 

Email spoofing is when an attacker forges email sender fields so a message appears to come from a trusted source. motive is social engineering, credential theft, fraud or bypassing simple filters.

Link : https://emkei.cz/

---


