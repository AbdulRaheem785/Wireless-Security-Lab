<p align="center">
  <img src="images/banner.png" width="100%">
</p>

<h1 align="center">📡 WPA/WPA2 Aircrack-ng Security Lab</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&pause=900&color=00FFCC&center=true&vCenter=true&width=900&lines=Wireless+Security+Assessment+Lab;Aircrack-ng+Handshake+Capture;WPA%2FWPA2+Security+Analysis;Cybersecurity+Learning+Project" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Kali-Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white">
  <img src="https://img.shields.io/badge/Aircrack--ng-Wireless-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/WiFi-Security-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Cybersecurity-Lab-red?style=for-the-badge">
</p>

---

# 📌 PROJECT OVERVIEW
━━━━━━━━━━━━━━━━━━━━━━━

Quick reference for capturing WPA/WPA2 handshakes and performing password security testing using Aircrack-ng in a controlled lab environment.

---

# ⚙️ ENVIRONMENT SETUP
━━━━━━━━━━━━━━━━━━━━━━━

- 🖥️ OS: Kali Linux (VMware / VirtualBox)
- 📡 Wireless Adapter: External USB (Monitor Mode supported)
- 🛠️ Tools: Aircrack-ng suite
- 📚 Wordlist: rockyou.txt

---

## 📸 Lab Setup

<p align="center">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/11.png?v=1775250630" width="85%">
</p>

---

⚠️ **IMPORTANT NOTICE**
━━━━━━━━━━━━━━━━━━━━━━━

> This project is strictly for **educational and authorized security testing only**.

---

# 🧩 LAB STEPS
━━━━━━━━━━━━━━━━━━━━━━━

---

## 🟢 STEP 1 — Check Wireless Adapter
━━━━━━━━━━━━━━━━━━━━━━━

<p align="center"> <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/1.png?v=1775249423" width="85%"> </p>

🔵 STEP 2 — Enable Monitor Mode

━━━━━━━━━━━━━━━━━━━━━━━

📸 Output
<p align="center"> <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/2.png?v=1775249423" width="85%"> </p>

🔴 STEP 3 — Kill Conflicting Processes

━━━━━━━━━━━━━━━━━━━━━━━

<p align="center"> <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/3.png?v=1775249422" width="85%"> </p>

🟣 STEP 4 — Scan Wireless Networks

━━━━━━━━━━━━━━━━━━━━━━━


<p align="center"> <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/4.png?v=1775249423" width="85%"> </p>
🟡 STEP 5 — Target Specific Network

━━━━━━━━━━━━━━━━━━━━━━━

📸 Output
<p align="center"> <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/5.png?v=1775249423" width="85%"> </p>
🟠 STEP 6 — Deauthentication (Lab Only)

━━━━━━━━━━━━━━━━━━━━━━━

<p align="center"> <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/6.png?v=1775249423" width="85%"> </p>
⚫ STEP 7 — Crack Captured Handshake

━━━━━━━━━━━━━━━━━━━━━━━

<p align="center"> <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/10.png?v=1775250340" width="85%"> </p>
⚪ STEP 8 — Wordlist Setup

━━━━━━━━━━━━━━━━━━━━━━━

<p align="center"> <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/9.png?v=1775250399" width="85%"> </p>
🔄 WORKFLOW SUMMARY

━━━━━━━━━━━━━━━━━━━━━━━

iwconfig
  ↓
airmon-ng start wlan0
  ↓
airmon-ng check kill
  ↓
airodump-ng wlan0
  ↓
target selection
  ↓
capture handshake
  ↓
deauth (lab)
  ↓
aircrack-ng attack
📚 KEY LEARNING OUTCOMES

━━━━━━━━━━━━━━━━━━━━━━━

Wireless network discovery
Monitor mode operations
Packet capture techniques
WPA/WPA2 handshake understanding
Dictionary-based security testing
Wireless security fundamentals
🛡️ ETHICAL NOTICE

━━━━━━━━━━━━━━━━━━━━━━━

🚫 Only use in authorized lab environments

✔ Allowed:

Cybersecurity training
Educational labs
Authorized testing
