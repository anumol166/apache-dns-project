# Troubleshooting Guide

This section documents real issues faced during Apache + DNS setup and how they were resolved.

---

## 1. dpkg Lock Error

**Error:**
Could not get lock /var/lib/dpkg/lock-frontend

**Cause:**
Another apt process was running in the background

**Solution:**
Checked running process and killed it:

sudo kill -9 <PID>

---

## 2. Apache Not Accessible

**Error:**
Website not loading in browser

**Cause:**
Apache service not started

**Solution:**
sudo systemctl start apache2
sudo systemctl enable apache2

---

## 3. Deleted Default Website Files

**Issue:**
After deleting /var/www/html content, website showed "Not Found"

**Cause:**
No index.html present

**Solution:**
Recreated index.html file:

sudo nano /var/www/html/index.html

---

## 4. DNS NXDOMAIN Error

**Error:**
nslookup myproject.local → NXDOMAIN

**Cause:**
System was using router DNS (192.168.18.1)

**Solution:**
Updated /etc/resolv.conf:

nameserver 127.0.0.1

---

## 5. Wrong IP Address

**Issue:**
Website not accessible from other devices

**Cause:**
Wrong IP used in DNS mapping

**Solution:**
Checked correct IP using:

ip a

Updated DNS zone file with correct IP

---

## 6. Website Not Accessible from Phone

**Issue:**
Could not access http://192.168.x.x from phone

**Cause:**
Wrong IP was used initially

**Solution:**
Used correct system IP and ensured same network

---

## 7. Bind9 Service Not Found

**Error:**
bind9.service not found

**Cause:**
Wrong service name used

**Solution:**
Correct service name:

sudo systemctl restart named

---

## 8. configs Folder Mistake

**Issue:**
Created 'configs' as file instead of directory

**Cause:**
Used nano instead of mkdir

**Solution:**
rm configs
mkdir configs

---

## 9. DNS Not Resolving Initially

**Issue:**
Domain not resolving even after configuration

**Cause:**
DNS service not restarted

**Solution:**
sudo systemctl restart named

---

## 10. Connection Failed (curl / browser)

**Error:**
Failed to connect to server

**Cause:**
Wrong IP address used

**Solution:**
Verified using:

ip a

Used correct IP

---

# Conclusion

This project helped in understanding real-world troubleshooting in:

* Package management
* Web server issues
* DNS configuration
* Network connectivity
* System services

