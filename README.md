# Benign

# 🕵️ TryHackMe: Benign - Splunk Lab Writeup

## 📝 Overview

This lab investigates a suspected compromise on a host in the HR department. Using Splunk to analyze Windows process creation logs (`Event ID: 4688`), we traced the attacker’s actions from initial access to payload download and post-exploitation. The logs were ingested into the `win_eventlogs` index, and user activity was correlated across departments.

### 🧑‍💼 Network Segmentation

- ** IT Department:** James, Moin, Katrina  
- ** HR Department:** Haroon, Chris, Diana  
- ** Marketing Department:** Bell, Amelia, Deepak   
---

## ❓ Questions & Answers

**1️⃣ How many logs are ingested from the month of March, 2022?**  



`13,959`

**2️⃣ Imposter account observed in the logs:**  



`Amel1a`

**3️⃣ Which HR user ran scheduled tasks?**  



`Chris.fort`

**4️⃣ Which HR user executed a system process to download a payload?**  



`Haroon`

**5️⃣ What system process (LOLBIN) was used?**  



`certutil.exe`

**6️⃣ Execution date of the binary:**  



`2022-03-04`

**7️⃣ Third-party site used for payload download:**  



`controlc.com`

**8️⃣ Name of file saved on the host machine:**  



`benign.exe`

**9️⃣ Malicious content/flag pattern:**  



`THM{KJ&*H^B0}`

**🔟 Full URL connected to:**  



`https://controlc.com/e4d11035`

---

## 🧩 Summary

Through Splunk analysis, we uncovered a malicious payload downloaded using `certutil.exe` by the HR user `Haroon`. A scheduled task was also configured by `Chris.fort`, indicating persistence. The attacker used an external paste site to host the payload and accessed it via a known LOLBIN. Indicators like the imposter user `Amel1a` further confirmed lateral movement and impersonation attempts.

---

## 📌 To-Do (You can fill this in)
