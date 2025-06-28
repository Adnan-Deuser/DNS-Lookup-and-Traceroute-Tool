# 🌐 DNS Lookup and Traceroute Tool – Python CLI

## 📌 Problem Statement

Diagnosing network connectivity issues or understanding the route a packet takes to reach a destination is essential in networking. This tool allows users to:

- Resolve domain names to IP addresses
- Measure network latency (ping)
- Trace the route taken by packets to reach a server

It mimics core functionalities of tools like `ping`, `tracert`, and `nslookup`.

---

## 💡 Project Overview

This is a **Python-based network diagnostic CLI tool** that performs:

- 🧭 DNS resolution (like `nslookup`)
- 📶 Latency checking (like `ping`)
- 🛣 Traceroute (like `tracert`)

Built for terminal use, it provides clear, readable output ideal for **technical users** or **network engineers**.

---

## ✨ Key Features                                                         
* 🧾 DNS Lookup        | Resolves domain names (e.g., `google.com`) to IP addresses using sockets    
* 📶 Latency Checker   | Sends multiple ICMP Echo requests to compute Round-Trip Times (RTTs)        
* 🛣 Traceroute         | Traces the packet path to the destination by incrementing TTL values        
* 📈 RTT Display       | Shows RTT for each hop in milliseconds                                      
* ❌ Timeout Handling  | Detects unreachable hops and displays "Request timed out" messages          

---

## 🛠 Technologies Used

| Technology | Purpose                                         |
|------------|-------------------------------------------------|
| Python 3   | Core programming language                       |
| `socket`   | DNS resolution using `gethostbyname()`          |
| `scapy`    | Sending and receiving raw IP/ICMP packets       |
| `time`     | Measuring round-trip latency                    |

---

## 🧠 Core Logic

- **DNS Lookup**:
  - Uses `socket.gethostbyname()` to resolve domain names to IP addresses.

- **Latency Check (Ping)**:
  - Sends ICMP Echo Requests using `scapy`.
  - Measures RTT using `time.time()` before/after sending.

- **Traceroute**:
  - Sends ICMP packets with increasing TTL (Time-To-Live) values.
  - Captures and prints each intermediate router's IP and RTT.

- **Timeout Handling**:
  - If no response is received within a timeout period, prints:
    ```
    * Request timed out
    ```

---

## 🧾 What I Learned

- 🌍 How DNS resolution works using sockets
- 🛰 Fundamentals of IP and ICMP protocols
- 🛣 How traceroute functions via TTL and ICMP Echo requests
- ⏱ Real-time performance measurement with millisecond precision
- 🧪 Sending and inspecting raw packets using Scapy
- 🖥 Building powerful command-line network utilities in Python

---

## 🖥 How to Run

1. **Install required modules**:
   ```bash
   pip install scapy
