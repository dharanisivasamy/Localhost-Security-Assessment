# 🔐 Localhost Security Assessment using Nmap & Wireshark

## 📌 Objective
To analyze locally running services, identify exposed ports, and inspect TCP communication using packet capture techniques.

---

## 🛠 Tools Used
- Kali Linux
- Nmap
- Wireshark
- Python HTTP Server

---

## 🔍 Methodology

### 1️⃣ Port Scanning
Performed SYN scan:
nmap -sS -sV 127.0.0.1

Result:
- Port 5432 open (PostgreSQL)

---

### 2️⃣ Service Exposure Testing
Started HTTP server:
python3 -m http.server 8080

Performed scan again to detect new open port.

---

### 3️⃣ Traffic Analysis
Captured packets on loopback interface using Wireshark.

Observed:
- TCP 3-way handshake
- HTTP GET request
- HTTP 200 OK response

---

## 📊 Findings
- PostgreSQL running locally on port 5432
- HTTP service exposed on port 8080
- Traffic transmitted in clear text (no encryption)
- Service bound to 0.0.0.0 increases exposure surface

---

## ⚠ Risk Analysis
- Unencrypted HTTP traffic can be intercepted
- Exposed services increase attack surface
- Misconfigured binding may allow external access

---

## ✅ Mitigation Recommendations
- Bind services to 127.0.0.1 when local-only
- Use HTTPS instead of HTTP
- Disable unused services
- Apply firewall rules

---

## 🎯 Conclusion
This project demonstrates practical understanding of port scanning, service enumeration, and packet-level traffic inspection using industry-standard tools.
