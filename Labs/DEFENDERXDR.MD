# APPLIED SKILL
##### [https://learn.microsoft.com/en-us/credentials/applied-skills/defend-against-cyberthreats-with-microsoft-defender-xdr/?wt.mc\_id=appliedskills\_cert\_as\_combination\_infographic\_marketingtoolkit\_wwl](https://learn.microsoft.com/en-us/credentials/applied-skills/defend-against-cyberthreats-with-microsoft-defender-xdr/?wt.mc_id=appliedskills_cert_as_combination_infographic_marketingtoolkit_wwl)

# Lab Guide: Protecting Computers with Microsoft Defender XDR

## **Introduction and General Rules**

This lab will teach you how to use a special security tool called **Microsoft Defender XDR** to stop "bad guys" (hackers) from hurting computers.

*   **Rule 1:** Always use the standard settings unless the instructions tell you to change something.
*   **Rule 2:** Only do exactly what is asked. Do not click extra buttons, as it might lower your score.
*   **Rule 3:** If there are two ways to do something, choose the easiest one.

* * *

## **Exercise 1: Preparing the Security Center**

**Goal:** Get the computer ready so we can start our security work.

1.  **Log in to Client2:** Use the username and password provided to sign in to the computer named **Client2**.
2.  **Open the Internet:** Open the **Microsoft Edge** browser.
3.  **Go to the Website:** Type `https://security.microsoft.com` in the top bar and sign in.
4.  **Find Incidents:** On the left menu, click **Investigation & response**, then click **Incidents & alerts**, and finally click **Incidents**.
5.  **Wait:** You will see a message saying "Hang on! We're preparing new spaces...". **Wait for 10 minutes** until it goes away.
6.  **Refresh:** Close the browser, then open it again and go back to `https://security.microsoft.com`.

* * *

## **Exercise 2: Adding Your Computer to the System**

**Goal:** Tell the security tool to watch over **Client2**.

### **Task 1: Create a Group**

1.  **Settings:** Click **Settings** at the bottom left.
2.  **Endpoints:** Click **Endpoints** and then **Device groups**.
3.  **Create Group:** Click **\+ Add device group**.
4.  **Name:** Type the name **Group1**.
5.  **Fix Problems:** Choose the setting that says **Remediate all threats automatically** (this means the computer fixes itself).
6.  **System:** Make sure it is set for **Windows 10 and 11**.

### **Task 2: Connect Client2**

1.  **Onboarding:** In the settings, find the word **Onboarding** and click it.
2.  **Domains:** Make sure it is set to recognize "simplified domains" (like `*.endpoint.security.microsoft.com`).
3.  **Download:** Click to download the "onboarding script" and save it in the **Downloads** folder on **Client2**.
4.  **Run:** Open your Downloads folder and run that script to connect the computer to the security tool.

### **Task 3: Test the Security**

1.  **Find the File:** Open the folder `C:\Files` on **Client2**.
2.  **Run Attack:** Right-click the **PowerShell script** there and click **Run with PowerShell**. (If you see an error about "Domain Controllers," just ignore it).

* * *

## **Exercise 3: Making a Security Rule (Policy)**

**Goal:** Block a specific type of virus. **Note:** Go to the computer named **Client1** to do this.

1.  **Endpoint Security:** In the portal, click **Endpoint security**.
2.  **Create Policy:** Create a new rule named **EndpointPolicy1**.
3.  **Block JavaScript:** Set the rule to **block** Windows 11 computers from using **JavaScript** to download and run dangerous files.
4.  **Who gets it?:** Assign this rule to the group called **sg-Executive**.

* * *

## **Exercise 4: Investigating the "Bad Guy"**

**Goal:** Find out what the hacker did and make a rule to stop them next time. **Note:** Stay on **Client1** for this.

### **Task 1: The Detective Work**

1.  **Find the Incident:** Go to the **Incidents** list and click on the one named **Multi-stage incident involving Defense evasion & Discovery on one endpoint**.
2.  **Look at the Timeline:** Click on **Client2** and look for a button called **Timeline**.
3.  **Find the IP:** Look for a "suspicious process injection". Write down the **IP address** (numbers like 1.2.3.4) and the **name of the file** it was trying to use.

### **Task 2: Set a Trap (Indicator)**

1.  **Indicators:** Go to **Settings** > **Endpoints** > **Indicators**.
2.  **Add:** Create a new one named **Indicator1** using the IP address you found.
3.  **Action:** Set it to **Block execution**.
4.  **Severity:** Set it to **High** for **Group1**.

### **Task 3: Automatic Alarm (Detection Rule)**

1.  **Hunting:** Click **Hunting** and then **Advanced hunting**.
2.  **The Secret Code:** Copy and paste this code (put the file name you found inside the quotes):
    
    קטע קוד
    
    ```
    DeviceProcessEvents
    | where InitiatingProcessFileName == "powershell.exe"
    | where FileName =~ "PUT_FILE_NAME_HERE"
    
    ```
3.  **Create Rule:** Click **Create detection rule** and name it **SuspiciousPowershell**.
4.  **Settings:** Set it to run **every hour** for **all devices**.
5.  **Result:** Tell it to **Collect investigation package** and mark the user as **Compromised**.

* * *

## **Exercise 5: Collecting Evidence and Locking Down**

**Goal:** Save the proof of the attack and stop the hacker from moving. **Note:** Stay on **Client1**.

1.  **Live Session:** Go to the page for **Client2** and click **Initiate Live Response session** to see what is happening right now.
2.  **Get Evidence:** Click the button **Collect investigation package** on the **Client2** page.
3.  **Save the File:** When it’s finished, find the file named `Forensics Collection Summary.csv` inside the package and save it to `C:\Files` on **Client1**.
4.  **Isolate:** Click **Isolate device** for **Client2**. This "locks" the computer so the hacker can't use it to attack anyone else.

* * *

**You are finished! You have successfully protected the network.**
