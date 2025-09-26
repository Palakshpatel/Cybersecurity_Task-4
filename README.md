# Elevate Labs Cyber Security Internship - Task 4: Setup and Use a Firewall on Windows

## Task Overview
[cite_start]The objective of this task was to configure and test basic firewall rules to allow or block traffic [cite: 4][cite_start], specifically demonstrating the configuration of an inbound block rule on a Windows system using Windows Firewall [cite: 5] [cite_start]for the Telnet port (23)[cite: 9].

## Deliverables
* **Screenshot 1.jpg:** Listing current firewall rules (Baseline).
* **Screenshot 2.png:** Configuration file showing the block rule applied.
* **Screenshot 3.png:** Screenshot showing the test of the block rule failing.

---

## 1. Documented GUI Steps Used (Windows Firewall)

| Step | Action | Purpose | Source Reference |
| :--- | :--- | :--- | :--- |
| **I. List Baseline Rules** | Opened **Windows Defender Firewall with Advanced Security** (`wf.msc`) and navigated to **Inbound Rules**. | Established baseline configuration. [cite_start]| [cite: 8] (Refer to **Screenshot 1.jpg**) |
| **II. Create Block Rule** | In **Inbound Rules**, clicked **New Rule** and created a rule to block inbound TCP traffic on port 23. | [cite_start]**Blocks inbound Telnet traffic.** | [cite: 9] |
| | - **Rule Type:** Port | | |
| | - **Protocol:** TCP, **Specific local ports:** 23 | | |
| | - **Action:** Block the connection | | |
| | - **Profile:** Domain, Private, Public | | |
| | - **Name:** `BLOCK Telnet Port 23 INBOUND` | | (Refer to **Screenshot 2.png**) |
| **III. Test the Rule** | Opened Command Prompt and ran `telnet 127.0.0.1 23`. | [cite_start]**Verified the block rule is functional.** | [cite: 10] |
| | - **Result:** "Connecting To 127.0.0.1...Could not open connection to the host, on port 23: Connect failed" | | (Refer to **Screenshot 3.png**) |
| **IV. Remove Test Rule** | Returned to **Inbound Rules**, right-clicked `BLOCK Telnet Port 23 INBOUND`, and selected **Delete**. | Restored the original firewall state. [cite_start]| [cite: 12] |

---

## 2. Summary: How a Firewall Filters Traffic

[cite_start]A firewall filters network traffic by enforcing a set of predefined security rules[cite: 4, 14]. [cite_start]It acts as a barrier [cite: 17] between a trusted network (or host) and an untrusted network (like the internet). [cite_start]The firewall examines data packets based on criteria such as the source and destination IP addresses, the protocol being used (e.g., TCP or UDP) [cite: 25][cite_start], and the port number[cite: 25].

* [cite_start]If a packet matches a rule that permits the connection (like an "Allow" rule), it is passed through[cite: 15].
* [cite_start]If a packet matches a rule that denies the connection (like the block rule for port 23 created in this task), the traffic is dropped or rejected[cite: 4, 15]. [cite_start]This traffic filtering mechanism is fundamental to improving network security[cite: 23].
