<h1>Phishing Analysis - Snapped Phish-ing Line Room on TryHackMe</h1>

<h2>Scenario</h2>

- <b>An Ordinary Midsummer Day...</b>
  - As an IT department personnel of SwiftSpend Financial, one of your responsibilities is to support your fellow employees with their technical concerns. While everything seemed ordinary and mundane, this gradually changed when several employees from various departments started reporting an unusual email they had received. Unfortunately, some had already submitted their credentials and could no longer log in.
  - You now proceeded to investigate what is going on by:
    -	Analyzing the email samples provided by your colleagues.
    -	Analyzing the phishing URL(s) by browsing it using Firefox.
    -	Retrieving the phishing kit used by the adversary.
    -	Using CTI-related tooling to gather more information about the adversary.
    -	Analyzing the phishing kit to gather more information about the adversary.

<h2>Languages and Utilities Used</h2>

- <b>Kali Linux</b>
- <b>Virus Total</b> 
- <b>Thunderbird</b>
- <b>CyberChef</b>
- <b>crt.sh</b>
- <b>HTML</b> 
- <b>Text Editor</b>
- <b>Firefox</b> 

<h2>Environments Used </h2>

- <b>Windows 11</b> (22H2)
- <b>Server 2022</b>

<h2>Program walk-through:</h2>

<p align="center">
<br />
Answer the questions below:  <br/>
<p>Q: Who is the individual who received an email attachment containing a PDF?
</p>

<p><b>A: William McClean</b>
<br />
  Because there was an email labeled “Quote for Services,” I chose it as my first email to investigate to see if there was an attached quote.
 
  ![image](https://github.com/user-attachments/assets/f4e1e46e-bba1-4093-8ac2-68b33f4fac9c)
  
  Here, we can see the email was sent to William McClean and there is an attached file Quote.pdf.
</b>
</p>

 ![image](https://github.com/user-attachments/assets/1190862d-b511-41d0-838b-52a2804f3e91)

<p>Q: What email address was used by the adversary to send the phishing emails?
</p>

<p><b>A: Accounts.Payable@groupmarketingonline.icu</b>
<br />
  We can see in the “From” section and in the message body that the adversary used the email address Accounts.Payable@groupmarketingonline[.]icu

<p>Q: What is the redirection URL to the phishing page for the individual Zoe Duncan? (defanged format)
</p>

<p><b>A: hxxp[://]kennaroads[.]buzz/data/Update365/office365/40e7baa2f826a57fcf04e5202526f8bd/?email=zoe[.]duncan@swiftspend[.]finance&error</b>

<br />
  I opened the email to Zoe
 
![image](https://github.com/user-attachments/assets/7057d91f-a5ce-45b1-8184-a4d6fde3a473)

<br />
  I opened the email in Thunderbird

![image](https://github.com/user-attachments/assets/8c64cf35-31ad-44c0-9afd-98ad1845eccc)

  
<br />
  Then I opened the email in Text Editor and searched for the attachment.

  ![image](https://github.com/user-attachments/assets/08238fe8-a056-4f93-884d-047e5779f158)

<br />
  I copied into CyberChef to decode from base64  

  ![image](https://github.com/user-attachments/assets/f1db8f77-d070-4e6c-8b39-b9b7486dcd00)

  
<br />
  As an alternative, the file can also be opened in Text Editor

  ![image](https://github.com/user-attachments/assets/b74e6378-ee4c-4efe-8ec4-04905bf068de)

  

