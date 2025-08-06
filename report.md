# Investigation Report: USPS-Themed Phishing Email Delivering NetSupport RAT

---

## Overview
On December 28, 2022, a phishing email disguised as a **USPS delivery notification** was identified.  
The message attempted to trick recipients into clicking malicious links by claiming that a shipment would be delivered soon.  
Further analysis confirmed that this email was part of a campaign delivering **NetSupport RAT (Remote Access Trojan)**.  

---

## Key Email Details
- **Date Received:** 28-Dec-2022  
- **Subject Line:** USPS.com package is at the store ready for delivery  
- **From:** USPostalService <waiania@soclar.net>  
- **Sender IP Address:** 35.196.193.120  
- **Return-Path:** waiania@soclar.net  
- **Authentication:** SPF – Failed, DKIM – Not Present, DMARC – Missing  
- **Attachments:** None  
- **Links:** Multiple embedded hyperlinks leading to non-USPS domains  

---

## Indicators of Malicious Intent

1. **Authentication Failures**  
   - SPF checks failed since the IP was not authorized for the soclar.net domain.  
   - DKIM signatures were absent, and no DMARC policy was configured.  
   - These failures strongly suggest spoofing.  

2. **Suspicious Domain**  
   - The sending domain `soclar.net` is not linked to USPS operations.  
   - Used exclusively to mislead recipients.  

3. **Urgency & Fake Package Notification**  
   - The email claimed the parcel would arrive *within 60 minutes*.  
   - Such urgency is a classic phishing technique to pressure quick clicks.  

4. **Deceptive Hyperlinks**  
   - Hovering over embedded text showed redirects to domains like:  
     - `http://lbbqyrluzu.cracknight23jm2-92501940h6.com/...`  
   - These clearly do not belong to USPS.  

5. **Generic Greeting**  
   - The email opened with “Hello,” instead of the recipient’s name.  
   - Legitimate USPS emails typically include customer-specific details.  

---

## Technical Header Review
- **X-Sender-IP:** 35.196.193.120  
- **Received From:** 218bc2699d9479f46ce65e550af1150d3 (unverified relay)  
- **Authentication Results:** SPF=Fail, DKIM=None, DMARC=Fail  
- **Message-ID:** <a7522897db99398bc064fe4185ae30f710c50@soclar.net>  

These attributes confirm the sender server is untrusted and unrelated to USPS.  

---

## Risks to Victims
- **Malware Installation:** Clicking the links initiates download of **NetSupport RAT**, giving attackers remote control over the device.  
- **Credential Harvesting:** Victims may unknowingly provide login information.  
- **Financial Exploitation:** Access to personal or banking accounts can lead to fraud.  
- **Data Breach:** Sensitive files and communications could be exfiltrated.  

---

## Defense Recommendations
- **Do Not Click:** Avoid interacting with any links in suspicious emails.  
- **Report the Incident:** Forward the email to USPS security and mark it as phishing.  
- **Block Malicious IP/Domains:** Deny traffic from IP 35.196.193.120 and domains linked in the email.  
- **Enable Strong Filters:** Ensure mail servers enforce SPF, DKIM, and DMARC checks.  
- **Raise User Awareness:** Educate users to recognize fake delivery notices and urgent messages.  
- **Endpoint Security:** Keep antivirus and anti-malware tools up to date.  

---

## Final Verdict
The email analyzed is a **phishing attempt** designed to impersonate USPS and deliver the **NetSupport RAT**.  
Its structure, failed authentication, fake links, and urgency tactics make it a clear security threat.  
Immediate blocking and user awareness are crucial to preventing compromise.  

---

*Report Author: Neha Chowdary*  
*Date: 06-Aug-2025*
