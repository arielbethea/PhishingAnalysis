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
</p>
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
  I copied and pasted it into CyberChef to decode from base64  

  ![image](https://github.com/user-attachments/assets/f1db8f77-d070-4e6c-8b39-b9b7486dcd00)

  
<br />
  As an alternative, the file can also be opened in Text Editor

  ![image](https://github.com/user-attachments/assets/b74e6378-ee4c-4efe-8ec4-04905bf068de)

  
<br />
  But back in CyberChef, I defanged the URL for safety

  ![image](https://github.com/user-attachments/assets/89f89b72-eccd-41e5-a41e-8ed836a253ea)

<br />
  Opening the attachment redirects you to the following page

  ![image](https://github.com/user-attachments/assets/a3b0a654-9161-4500-ae13-826cbc0e84cf)


<p>Q: What is the URL to the .zip archive of the phishing kit? (defanged format)
</p>

<p><b>A: hxxp[://]kennaroads[.]buzz/data/Update365</b>
<br />  

<p>Q: What is the SHA256 hash of the phishing kit archive?
</p>

<p><b>A: ba3c15267393419eb08c7b2652b8b6b39b406ef300ae8a18fee4d16b19ac9686</b>
<br />
	I entered the URL in the Firefox browser

 ![image](https://github.com/user-attachments/assets/50a12596-1a1d-402a-8ee9-61b44bfaeef0)

 <br />
	I downloaded the File, accessed in Terminal, and found the SHA256 hash

  ![image](https://github.com/user-attachments/assets/c391fc95-2c37-4f59-86a3-a0168f3f0b82)

  
<p>Q: When was the phishing kit archive first submitted? (format: YYYY-MM-DD HH:MM:SS UTC)
</p>

<p><b>A: 2020-04-08 21:55:50 UTC</b>
<br />
	
  ![image](https://github.com/user-attachments/assets/4cba6bdb-2d8d-4ccb-adcf-76a16108aa34)

  ![image](https://github.com/user-attachments/assets/8b2cab2a-5095-4646-894a-98457f0078d0)

  
<p>Q: When was the SSL certificate the phishing domain used to host the phishing kit archive first logged? (format: YYYY-MM-DD)
</p>

<p><b>A: 2020-06-25</b>
<br />

  ![image](https://github.com/user-attachments/assets/2c07d940-8e53-41bd-8c76-d1408a5b6378)

  ![image](https://github.com/user-attachments/assets/1096e978-4db9-436e-bed2-a52397acdd03)

  
<p>Q: What was the email address of the user who submitted their password twice?
</p>

<p><b>A: michael.ascot@swiftspend.finance</b>
<br />

  ![image](https://github.com/user-attachments/assets/157c043f-d191-4d05-b4f7-29f9341052e4)


<p>Q: What was the email address used by the adversary to collect compromised credentials?
</p>

<p><b>A: m3npat@yandex.com</b>
<br />

  ![image](https://github.com/user-attachments/assets/ede0be1c-5532-4b5a-844d-c733cdddb440)

  ![image](https://github.com/user-attachments/assets/7c0ebde3-a2a6-4938-becc-747b1e0bd1d1)

  ![image](https://github.com/user-attachments/assets/cb7361d7-7b35-4853-8db0-77fabc0d9e79)

  
<p>Q: The adversary used other email addresses in the obtained phishing kit. What is the email address that ends in "@gmail.com"?
</p>

<p><b>A: jamestanner2299@gmail.com</b>
<br />

  ![image](https://github.com/user-attachments/assets/91a35db9-31f1-4347-b262-08e841bd89a7)

  ![image](https://github.com/user-attachments/assets/d53a4af9-772b-4eb7-941d-2f504753adab)
  
<p>Q: What is the hidden flag?
</p>

<p><b>A: THM{pL4y_w1Th_tH3_URL}</b>
<br />

  ![image](https://github.com/user-attachments/assets/2836c305-081e-4af0-83ba-3d62e223b07c)

  ![image](https://github.com/user-attachments/assets/e0c1b537-1226-4100-b60d-1bd9fc931522)

  ![image](https://github.com/user-attachments/assets/119b7846-204f-454a-b8cf-195cceabcf8d)

  



  

 

