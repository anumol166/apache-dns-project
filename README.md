# Apache + DNS Project

## 📌 Overview

This project demonstrates hosting a website using Apache and configuring a custom domain using Bind9 DNS server in Linux.

## ⚙️ Technologies Used

* Linux (Kali)
* Apache2
* Bind9

## 🌐 Project Flow

User → DNS → IP → Apache → Website

## 🔧 Features

* Web server setup using Apache
* Custom domain (myproject.local)
* DNS configuration using Bind9
* Troubleshooting real-world issues

## 📁 Project Structure

* commands/ → setup commands
* configs/ → DNS configuration files
* website/ → HTML file
* screenshots/ → proof of working
* troubleshooting.md → issues & fixes

## 🚀 Outcome

Successfully hosted a website and resolved it using a custom DNS server within a local network.

## 👨‍💻 Author

Anumol Varghese


⚠️ DNS Configuration Note & Learning

During this project, the DNS setup was performed in multiple stages, which resulted in different IP addresses being used in configuration files and screenshots.

Initial Setup (Network Access)
Used system IP: 192.168.18.154
Purpose: To allow access from other devices within the same network
Later Setup (Local Testing)
Updated DNS mapping to: 127.0.0.1
Purpose: To test DNS resolution locally within the same system
Why Different IPs Were Used?
192.168.18.154 → Used for network-based access
127.0.0.1 → Used for local loopback testing
DNS Resolution Behavior
After configuring Bind9 as the local DNS server, the system resolver (/etc/resolv.conf) was updated to use:
nameserver 127.0.0.1
That is why nslookup shows the server as 127.0.0.1
Key Learning Outcomes
Understood the difference between local DNS resolution and network DNS resolution
Learned how IP mapping affects accessibility across devices
Gained hands-on experience in DNS troubleshooting and configuration in Linux
