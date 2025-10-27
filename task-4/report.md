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

#### In your limux machine 

- open terminal and enter command `sudo ufw status`


      sudo ufw status

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
  
