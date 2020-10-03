---
layout: post
title: # New service checks if your email was used in an Emotet spam campaign
tags: [security]
---

![]({{ site.baseurl }}/blog/assets/images/emotet.jpg)

Italian cybersecurity company TG Soft has launched a new service called ["Have I Been Emotet"](https://www.haveibeenemotet.com/), which allows users to check if a domain or email address has been used as a sender or recipient of an Emotet spam campaign.

Emotet is malware that spreads through spam emails, which contain malicious Word or Excel documents. When a user opens these documents and the macros are enabled, the Emotet trojan will be installed on their computer.
<!--more-->
After infecting the victim's computer, Emotet steals the email and transmits it to servers under the attacker's control. This email will be used in future spam campaigns, allowing the malicious agent to make the malicious unwanted content appear legitimate in order to attract more victims.

Over time, the Emotet trojan downloads and installs other malware, such as TrickBot and QakBot, onto a victim's computer. These trojans lead to ransomware attacks performed by Ryuk, Conti and ProLock operators.

TG Soft told BleepingComputer that their database consists of controlled outgoing emails created by Emotet between August and September 23, 2020. During this period, they collected over 2.1 million email addresses from approximately 700,000 outgoing emails.

To use this new service, one can enter a domain or email address and receive updates on how many times they have been used as a sender or recipient of an Emotet spam campaign.

The "Have I Be Emotet" service provides users with the following information:

- Real sender: Indicates that the computer using this email account has been compromised and has been used to send spam emails.

- Fake sender: Indicates that your mail has been stolen and used in spam campaigns.

- Recipient: Indicates that you have received an Emotet spam email.

If a company has been affected by a cyberattack, one can check if it has been targeted by Emotet spam campaigns, leading to a ransomware attack. Ryuk ransomware, for example, recently attacked the leading Universal Health Services (UHS) healthcare provider. Using this service, we can see that the UHS domain, uhsinc.com, has been used in recent Emotet campaigns and that the company has received Emotet spam nine times.

![]({{ site.baseurl }}/blog/assets/images/emo.png)

If someone uses this service and finds that their email address or domain has been used as a recipient, this does not necessarily mean that you are infected. To be infected, a user must open their email attachments and enable macros before installing the malware. In addition, if a user's domain has users who refer to it as a "real" sender, then it is possible that one of their email domain users is infected and their computers should be thoroughly scanned.