# USPS Phishing Email Analysis (NetSupport RAT Case Study)

## 🌐 About This Project
Hi there! 👋  
This project is all about digging into a phishing email that pretended to come from the **United States Postal Service (USPS)**.  
The email looked like a normal delivery update, but in reality, it was a trick to get people to click on fake links.  
Those links led to a dangerous piece of malware called **NetSupport RAT**, which can give attackers full access to someone’s computer.

I went through the email step by step — checking its headers, looking at the content, and pulling out the suspicious links — to show how these kinds of attacks work and why they’re so dangerous.  

---

## 📂 What’s Inside
- **report.md** → The full detailed analysis of the phishing email  
- **screenshots/** → Images of the investigation (headers, content, suspicious links)  
- **readme.md** → This file, giving you the big picture  

---

## 🕵️ My Key Findings
Here’s what stood out during the investigation:

- The email was sent from a **fake domain** (`soclar.net`), not USPS.  
- Security checks like SPF, DKIM, and DMARC all **failed** — a big red flag.  
- It tried to create **urgency**, saying the package would be delivered in *60 minutes*.  
- The “USPS” links actually went to **weird domains** that had nothing to do with USPS.  
- If clicked, it would download **NetSupport RAT** (a Remote Access Trojan).  

---

## ⚠️ Why It’s Dangerous
If someone fell for this email, the attacker could:  
- Take control of the victim’s computer remotely  
- Steal personal and banking credentials  
- Spy on files, emails, and private data  
- Use the victim’s identity for fraud or more attacks  

---

## 🔐 How To Stay Safe
- **Don’t click** links in suspicious emails, even if they look urgent  
- **Double‑check the sender** by going to the official USPS website  
- **Report phishing** emails instead of ignoring them  
- **Use filters** (SPF, DKIM, DMARC) to block fake emails  
- **Educate yourself and others** — awareness is the best defense  
- **Keep your security software updated**  

---

## 👩‍💻 About Me
- **Author:** Neha Chowdary  
- **Date:** August 6, 2025  

I created this project to help others understand how phishing works and to spread awareness about how easy it is to get tricked if we’re not careful.  

---

## 📌 Note
This research is for **educational purposes only**.  
Please don’t try to visit any of the malicious links shown in the screenshots or the report.  
Stay safe!  
