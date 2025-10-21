[Task 2: Web Application Analysis with Burp Suite](#task-2-web-application-analysis-with-burp-suite)
- [Objective](#objective)
- [Tools](#tools)
- [Hints](#hints)
- [Task Solution](#task-solution)


# Task 3: Analyze a Phishing Email Sample

## Objective: 
-  Identify phishing characteristics in a suspicious email sample

  ## Tools:
- Email Client
- Header Analyzer.

## Hints

1.Obtain a sample phishing email (many free samples online).

2.Examine sender's email address for spoofing.

3.Check email headers for discrepancies (using online header analyzer).

4.Identify suspicious links or attachments.

5.Look for urgent or threatening language in the email body.

6.Note any mismatched URLs (hover to see real link).

7.Verify presence of spe ling or grammar errors.

8.Summarize phishing traits found in the email.

## Task Solution

### 1. Obtain a sample phishing email.
<br>

 🌐 [template](https://th3nobody.github.io/cybersecurity/task-3/assets/templats.html) 
 
 <br>

![img not found](assets/template-sample.png)

<br>

### when sent to victim it looks like
  
  <br><br>
  
  ![img not found](assets/mail-sample.png) 

### 2. Examine sender's email address.

- As seen in the image this mail was send by gophish using email `ajalto32@gmail.com`

   ![img not found](assets/header.png)
  
<br>

  ![img not found](assets/origin.png)

- Here in this mail X-Google-Original-From is set to  `security@mail.instagram.com`
  

      X-Google-Original-From: security@mail.instagram.com

  <br>

- And X-Mailer is `gophish`


      X-Mailer: gophish
  

### 3. Check email headers for discrepancies

 ![img not found](assets/del-info.png)

 <br>

 ![img not found](assets/relay-info.png)

<br>


   ![img not found](assets/analysis.png)

 <br>


### 4. Identify suspicious links or attachments.

- On checking every clickable link i found that every link redirects to same site.


<br> 
  
- link :

      https://largely-helpful-swift.global.ssl.fastly.net/NTQzYWNjMTAxMzkzM2MyYmM4MmE1YQ==/ig-en.php?profileid=780849966&amp;auth=OWZhMzQ1ZmExOGU3MGI4NzZjZGYzMA==

   ![img not found](assets/email-link.png)

  <br>

- #### while visiting the link there was a instagram clone like website.

  <br>

 ![img not found](assets/link.png)  

 <br>

 

