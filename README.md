# 🏢 Integrated Smart Office Network with Static Routing and Wireless Access

## 📘 Project Overview
This project involves designing and configuring an integrated **Smart Office Network** using **Cisco Packet Tracer**.  
The goal is to create a functional medium-sized office setup with **three wired LANs** and **one wireless guest network**, all interconnected via **static routing**.

---

## 🎯 Objectives
- Design **3 LANs** (HR, IT, Sales) and **1 WLAN** (Guest Wi-Fi Zone).
- Configure **static routing** between all networks using two interconnected routers.
- Connect **smart IoT devices** (e.g., light and thermostat) through a wireless router.
- Enable a **centralized Web/DNS server** for internal access.
- Verify end-to-end communication between all departments and the web server.

---

## 🧩 Network Design Summary

| Department / Zone | Network Address | Devices | Connection |
|-------------------|-----------------|----------|-------------|
| HR                | 192.168.10.0/24 | 3 PCs, 1 Switch | Router 1 |
| IT                | 192.168.20.0/24 | 2 PCs, 1 Server (Web + DNS), 1 Switch | Router 1 |
| Sales             | 192.168.30.0/24 | 2 PCs, 1 Laptop, 1 Switch | Router 2 |
| Guest Wi-Fi       | 192.168.40.0/24 | Smart Light, Thermostat, Wireless Router | Router 2 |

### Devices Used
- **Routers:** 2 × Cisco 2911/2811  
- **Switches:** 3 × Cisco 2960  
- **Wireless Router:** 1  
- **Computers:** 8 PCs + 2 Laptop  
- **Server:** 1 Web/DNS Server (in IT LAN)  
- **Smart Devices:** IoT Light + Thermostat  

---

## ⚙️ Configuration Details

### IP Addressing 
| Network | Subnet Mask | Default Gateway | Example Host IPs |
|----------|--------------|----------------|------------------|
| HR | 255.255.255.0 | 192.168.10.1 | 192.168.10.2–192.168.10.4 |
| IT | 255.255.255.0 | 192.168.20.1 | 192.168.20.2–192.168.20.4 |
| Sales | 255.255.255.0 | 192.168.30.1 | 192.168.30.2–192.168.30.4 |
| Guest Wi-Fi | 255.255.255.0 | 192.168.40.1 | 192.168.40.2–192.168.40.4 |

### Static Routing Example
On **Router 1**:
ip route 192.168.30.0 255.255.255.0 <Router2_Serial_IP>
ip route 192.168.40.0 255.255.255.0 <Router2_Serial_IP>
On **Router 2**:
ip route 192.168.10.0 255.255.255.0 <Router1_Serial_IP>
ip route 192.168.20.0 255.255.255.0 <Router1_Serial_IP>

### Wireless Configuration
- **SSID:** Wi-Fi Zone  
- **Security:** WPA2-PSK  
- **Password:** 12345678
- Connect IoT Light and Thermostat to this network.

### Server Configuration
- **Web Server:** Enabled (HTTP + HTTPS)
- **DNS Server:** Enabled
- Add A-records for internal hosts (www.projectwebsite.co)

---

## ✅ Verification
- **Ping Tests:** Successful ping between all LANs and Web Server.  
- **Web Test:** Access `http://192.168.20.2` or `http://www.projectwebsite.com` from any PC.  
- **IoT Test:** Smart Light and Thermostat accessible via Wireless Router.

---

## 🧠 Why Static Routing?
Static routing was chosen for **simplicity, predictability, and control**.  
Since the topology is small and stable, static routes minimize overhead and ensure reliable inter-department communication without the complexity of dynamic routing protocols.

---

---

## 🧰 Tools Used
- Cisco Packet Tracer

---

