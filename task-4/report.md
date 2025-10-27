[ Task 4 : Setup and Use a Firewall on Windows/Linux](#task-4--setup-and-use-a-firewall-on-windowslinux)
- [Objective](#objective)
- [Tools](#tools)
- [Hints](#hints)
- [Task Solution](#task-solution)

#  Task 4 : Setup and Use a Firewall on Windows/Linux

## Objective: 
-  Configure and test basic firewall rules to allow or block traffic.

  ## Tools:
- Windows Firewall
- ufw
- iptables 
- nftables

## Hints

1.Open firewall configuration tool (Windows Firewall & terminal ).

2.List current firewall rules.

3.Add a rule to block inbound traffic on a specific port (e.g., 23 for Telnet).

4.Test the rule by attempting to connect to that port locally or remotely.

5.Add rule to allow SSH (port 22) if on Linux.

6.Remove the test block rule to restore original state.

7.Document commands or GUI steps used.

8.Summarize how firewall filters traffic.

## Task Solution

---

### 1. Open firewall configuration tool

#### In your windows pc:

- go to control panel then system and security then windows defender firewall

- Then click to Advanced setting

 ![img not found](assets/control-p.png)

 <br>

- after clicking advanced setting you will abl to see windows defender rules and configurations

<br>

   ![img not found](assets/advances-s.png)

#### In your limux machine: 

- open terminal and enter command `sudo ufw status`


      sudo ufw status

- if it shows inactive enter command `sudo ufw enable` to activate firewall.

   ![img not found](assets/ufw.png)

---

### 2. List current firewall rules.

#### In your windows pc:

- in the left side of your windows defender firewall with advance setting click:
  

  - inbound rules to see all inbound rules set in windows defender firewall <br>


   ![img not found](assets/in-rules.png) <br>
   

  - outbound rules to see all inbound rules set in windows defender firewall

<br>


![img not found](assets/out-rules.png)
  
<br>

#### In your limux machine:

- enter command `sudo ufw status numbered` to see all used rules

      sudo ufw status numbered

- if no rules are listed and only `status: active` message is received then no rules have been made in that systeme.

<br>

 ![img not found](assets/linux-rules.png) <br>

 
---

 ### 3. Add a rule to block inbound traffic on a specific port (e.g., 23 for Telnet)

 #### In your windows pc:


- after going to in/out bound rules click in new rules

- set rule types to port

   <br>
  
  ![img not found](assets/rule-prt.png)
  
  <br>

- protocol to tcp or udp to 23 ( 23 is for telnet)

   <br>
  
  ![img not found](assets/prt.png)
  
  <br>

- in action section select what this is rules is supposed to do:
  - allowing this connection
  - or allowing is secure
  - or blocking connection

     <br>
  
  ![img not found](assets/act.png)
  
  <br>

- then set what types of network profile is this rules applied to (eg: private, public)

   <br>
  
  ![img not found](assets/profile.png)
  
  <br>

- in the end give name and description to rule which will later help to recognize the rule.

   <br>
  
  ![img not found](assets/rule-name.png)
  
  <br>

- Now the rule to block telnet connection have been saved.

  <br>

#### In your limux machine:
  
- in your linux terminal enter `sudo ufw deny 23/tcp` to block port 23 with tcp protocal (i.e telnet)

      sudo ufw deny 23/tcp

<br>

   ![img not found](assets/rules-set.png)
  
<br>

--- 

### 4. Test the rule by attempting to connect to that port locally or remotely.


#### In your limux machine:

- in your linux terminal enter command `telnet localhost 23` to check connection

      telnet localhost 23

   ![img not found](assets/con-test.png)

<br>

- sincee rule is active the connection failed

  <br>

  ---

### 5. Add rule to allow SSH (port 22) if on Linux.

- in linux terminal enter command `sudo ufw allow 22` to allow SSH

   ![img not found](assets/ssh-allow.png)

  <br>
  
---

### 6. Remove the test block rule to restore original state.

#### In your limux machine:

- in your linux terminal enter command `sudo ufw delete deny 23/tcp` and `sudo ufw delete allow 22`

  ![img not found](assets/delete-rules.png)

  <br>

---

### 7. Document commands or GUI steps used.

#### In your windows pc: 

 ![gif not found](assets/in-bound.gif)

<br>

#### In your limux machine:

 ![gif not found](assets/rule-set.gif)

- Following these simple GUI steps shown in this gif you can make changes in rules of firewals used in your windows or linux system.

  <br>

  ---

  



  
