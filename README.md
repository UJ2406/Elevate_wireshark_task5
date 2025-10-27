# 📡 Wireshark Network Traffic Analysis (Task 5)

## 📋 Task Overview
Captured and analyzed live network packets using Wireshark on Kali Linux, filtered by protocol, and documented different types of network traffic.

---

## 🎯 Objectives
- Capture live packets on the real interface using Wireshark.
- Identify and analyze at least three major network protocols.
- Export findings with `.pcap` and documentation.
- Answer assigned interview questions for reporting.

---

## 🛠️ Tools Used
- 🐧 Kali Linux
- 🔬 Wireshark

---

## ⚙️ Methodology

### 1️⃣ **Installation**

```
sudo apt update
sudo apt install wireshark
sudo usermod -aG wireshark $USER
```

### 2️⃣ **Capture Traffic**
- Started Wireshark
  ```
  wireshark
  ```
- Selected active interface (eth0/wlan0).
- Clicked the blue shark fin to begin capturing.

### 3️⃣ **Generate/Observe Traffic**
- Ran `ping google.com` to generate ICMP/DNS traffic.
- Opened Firefox/Chromium, browsed `example.com`, and searched to generate HTTP/HTTPS packets.

### 4️⃣ **Apply Protocol Filters**
- **tcp** → Displays Transmission Control Protocol traffic.
- **dns** → Displays Domain Name System queries/responses.
- **http** → Captures Hypertext Transfer Protocol packets.


### 5️⃣ **Protocol Analysis Table**

| Protocol | Filter | Example Frame(s) | What it Shows                                  |
|----------|--------|------------------|------------------------------------------------|
| TCP      | tcp    | 410, 411         | Connections; handshake, reliable data transfer  |
| DNS      | dns    | 0–17             | Domain lookups, standard queries/responses      |
| HTTP     | http   | 412–1498         | Web requests (`GET`/`POST`) and web responses   |

### 6️⃣ **Save .pcap File**
- File → Export Specified Packets → Save as `.pcap`.

---

## 📝 Interview Questions & Answers

**1. What is Wireshark used for?**  
Wireshark is a packet analyzer that captures and displays network traffic in real time for troubleshooting, analysis, and cybersecurity investigations.

**2. What is a packet?**  
A unit of data transmitted over a network, containing payload plus protocol-specific header info.

**3. How do you filter packets in Wireshark?**  
Type protocol or conditions (e.g., `tcp`, `dns`, `http`, or `ip.addr == 8.8.8.8`) in the display filter bar.

**4. What is the difference between TCP and UDP?**  
TCP is connection-oriented, reliable, and slower (handshake, retransmission of lost packets); UDP is connectionless, faster, and less reliable (no retransmission, often used for streaming/DNS).

**5. What is DNS traffic?**  
Domain Name System traffic; resolves domain names (like google.com) to IP addresses.

**6. What does HTTP traffic reveal?**  
Web traffic requests/responses; exposes GET/POST data/headers (unencrypted unless using HTTPS).

**7. What is a .pcap file?**  
A packet capture file containing raw network traffic for later analysis in Wireshark or similar tools.

**8. Why is protocol distinction important in cybersecurity?**  
Identifying traffic types enables detection of suspicious/malicious activity and understanding network behavior for defense or response.

---

## 🚀 Key Takeaways

- Network protocols (TCP, DNS, HTTP) are fundamental to online communication.
- Wireshark’s filters (`tcp`, `dns`, `http`, etc.) let you isolate and analyze precise traffic types.
- Capturing on the correct interface and generating test traffic is crucial for seeing relevant results.
- Protocol analysis allows identification of system activity, troubleshooting, and detection of attacks or leaks.

---

## 🧠 Concepts Learned

- **Capture and protocol analysis:** Used Wireshark to view live network activity and filter by protocol.
- **TCP:** Understood connection setup/teardown (SYN/ACK), transmission, and handshakes.
- **DNS:** Saw domain-to-IP queries, resolution cycles as browsers access sites.
- **HTTP:** Observed web requests/responses directly (on unencrypted HTTP).
- **The importance of the right interface:** Proper setup and traffic generation are required for meaningful results.
- **Cybersecurity relevance:** Packet analysis is central for defenders (IDS/IPS), digital forensics, and attackers in enumeration or data exfiltration.

---

## 📂 Repository Structure

```
wireshark-analysis-task5/
├── README.md               # This file
├── wshk.pcap               # Saved Wireshark capture
├── screenshot/             # Images of the task
  ├── installation.png
  ├── settinguser.png
  └── mainmenu.png
  └── dnsfilter.png
  └── httpfilter.png
  └── tcpfilter.png
├── finding.txt            # Summary of protocol findings
```
