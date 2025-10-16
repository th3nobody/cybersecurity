[Task 2: Web Application Analysis with Burp Suite](#task-2-web-application-analysis-with-burp-suite)
- [Objective](#objective)
- [Tools](#tools)
- [Hints](#hints)
- [Task Solution](#task-solution)
  - [1. Setup](#1-setup)
  - [2. Intercept](#2-intercept)
  - [3. Probe Manually](#3-probe-manually)
  - [4. Decode Data](#4-decode-data)
  - [5. Set Up Attack](#5-set-up-attack)
  - [6. Launch Attack](#6-launch-attack)
  - [7. Analyze Results](#7-analyze-results)
  - [8. Compare to Confirm](#8-compare-to-confirm)



# Task 2: Web Application Analysis with Burp Suite

## Objective: 
- To learn the end-to-end process of identifying and analyzing a potential web vulnerability by intercepting <br>traffic, manually probing, running an automated attack, and comparing the results using Burp Suite's<br> integrated tools

  ## Tools:
- Burp Suite
- firefox browser
- foxy proxy (firefox extension)

  ## Hints

  1.Setup: Configure your browser to proxy through Burp Suite (127.0.0.1:8080) and install the CA certificate.

  2.Intercept: Use Proxy > Intercept to capture a login request from a practice website. Modify it and forward <br> to see the effect.

  3.Probe Manually: Find the request in Proxy > HTTP history, right-click, and "Send to Repeater". In Repeater,<br> modify parameters (like adding a ' to test for SQLi) and resend to analyze responses.

  4.Decode Data: If you see encoded text (like Base64) in Repeater, send it to the Decoder tab to view, modify,<br> and re-encode it for further testing.

  5.Set Up Attack: Right-click the request in Repeater and "Send to Intruder". In the Positions tab, clear default<br>
   selections (§) and mark only the password field as the payload position.

  6.Launch Attack: In the Payloads tab, load your password wordlist. Set the attack type to Sniper and click "Start<br>
   attack".
  
  7.Analyze Results: In the Intruder results window, sort by the "Length" column. A response with a different length<br>
    likely indicates a successful login.
  
  8.Compare to Confirm: Send one failed response and the suspected successful response to the Comparer tab. <br>Perform a
    "Words" comparison to visually confirm the differences and validate your findings.

  ## Task Solution

  ### 1. Setup:

- Install foxyproxy extension [for chromium web browser](https://chromewebstore.google.com/detail/foxyproxy/gcknhkkoolaabfmlnjonogaaifnjlfnp) and [for firefox](https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search)
- Add 127.0.0.1 as hostname and 8080 as port in the foxyproxy extension
   ![img not found](assets/foxy-proxy.png)
- go to [http://burp/](http://burp/) and download CA Certificate.
 ![gif not found](assets/crt-install.gif)
- Now burp is ready to capture requests.
 ### 2. Intercept:
- select burp from your foxyproxy extension.
- open target website enter login details.
- check in http history section, you will find all request made from your browser.
- send it to repeter and try modifing it and observe response from server.
 ![img not found](assets/login-req-captured.png)

### 3. Probe Manually:

- Right click your login request and select send to Repeater.
- I tried adding `'--` after email address.
- And found this login page is vulnerable to Sql injection.
 ![img not found](assets/sql-injection.png)

### 4. Decode Data:
- There was a encoded text in the login dashboard.

      Q29uZ3JhdHVsYXRpb25zISBZb3UgaGF2ZSBzdWNjZXNzZnVsbHkgc29sdmVkIHRoZSBsYWIgZGVzaWduZWQgYnkgQXNtaWssICRGTEFHe2FzbTFrX3J1bDN6XzBubHl9IyQ=.
- Select the encoded text and right click it then select send to decoder.
- Select decode as Base64
![img not found](assets/msg-decoded.png)
- And found flag : `$FLAG{asm1k_rul3z_0nly}#$.`

       $FLAG{asm1k_rul3z_0nly}#$.

### 5. Set Up Attack:

- Right-click the request in Repeater and "Send to Intruder".
- In the Positions tab, clear default selections (§).
- And mark only the password field as the payload position.
![img not found](assets/intruder-payload.png)

### 6. Launch Attack: 
- In payload option click load and select file will potential password.
- Set the attack type to Sniper and click "Start attack".
  ![img not found](assets/intruder-payload.png)

### 7. Analyze Results:
- let the attack be completed.
- Sort by the "Length" column, the different in response length is likely the one with successful login.

   ![gif not found](assets/intruder-brute.gif)

### 8. Compare to Confirm: 

- Send one failed response and the suspected successful response to the Comparer tab.
- Perform a "Words" comparison to visually confirm the differences and validate your findings.
![img not found](assets/compare.png)
- while comparing two response I found my intruder attack was sucessfull.
- And found that password was `test`
  
  ---

  
