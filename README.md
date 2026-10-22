# DEDSEC: Demonstrating Effective Defense and Security Exploitation for Connected Devices
*PX505 Innovation Project – Grenoble INP - Esisar (2024–2025)*

## Overview
**DEDSEC** is an educational cybersecurity toolkit and demonstration framework designed to evaluate and expose common vulnerabilities in Internet of Things (IoT) smart home ecosystems. Developed as part of an innovation project at Grenoble INP - Esisar, this project demonstrates how relatively simple, low-cost equipment and open-source tools can compromise real-world IoT protocols[cite: 6, 8].

---

## Key Scenarios & Attack Vectors

### 1. Smart Plug Wi-Fi Deauthentication Attack
* **Target Hardware:** Sonoff S26 Smart Plug controlling a simulated smart irrigation water pump[cite: 6, 11].
* **Protocol:** WPA/WPA2[cite: 12].
* **Execution:** Utilized a Linux host with a Wi-Fi adapter in monitor mode and `aircrack-ng` / `aireplay-ng` to capture EAPOL handshake packets and launch directed deauthentication frames[cite: 15, 20].
* **Impact:** Forcefully disconnected the smart plug from the local access point, disabling remote smartphone control (`eWeLink` app) and causing device state persistence (water pump remaining stuck in its last active state)[cite: 11, 12, 14].

### 2. Bluetooth Low Energy (BLE) Man-in-the-Middle (MITM) Attack
* **Target Hardware:** 6TRON / Z_Motion environmental sensor measuring temperature and humidity[cite: 11, 23].
* **Protocol:** Bluetooth Low Energy (BLE)[cite: 12].
* **Execution:** Used dual BLE dongles running Linux-based offensive frameworks (**Mirage** and **Whad**) to scan, clone device characteristics (MAC address and GATT services), and intercept data streams between the sensor and the user's mobile app[cite: 16, 22, 25].
* **Impact:** Successfully spoofed the BLE peripheral, relaying falsified environmental telemetry data to the smartphone application to trigger incorrect automated irrigation decisions[cite: 12, 17].

---

## Tech Stack & Tools Used
* **Operating System:** Linux (Kali / Ubuntu)[cite: 13, 14]
* **Wireless & Network Security:** Wireshark, Aircrack-ng suite (`aireplay-ng`, `aircrack-ng`)[cite: 12, 20]
* **BLE Auditing Frameworks:** Mirage, Whad (`wble-central`), `hcitool`[cite: 17, 23, 25]
* **Hardware:** Alfa/Compatible Wi-Fi Antenna (Monitor Mode), Dual BLE USB Dongles, Sonoff S26 Smart Plug, 6TRON Sensor[cite: 11, 14, 16]

---

## Documentation & Report
The complete academic evaluation, methodology, architecture diagrams, and command-line execution logs are available in the repository:
- 📄 [View Final Project Report (PDF)](./DEDSEC_2024_2025%20Final%20Report.pdf)

---

## Authors & Contributors
* **Nguyen Van Binh Julien**[cite: 6]
* **Attia Sara**[cite: 6]
* **Muhammad Waseem**[cite: 6]
