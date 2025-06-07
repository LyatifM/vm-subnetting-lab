# vm-subnetting-lab
Manual subnetting lab using a /26 mask to assign static IPs on a Windows host and Ubuntu VM, then verify connectivity with ping.
# Creating a Subnet and Testing Connectivity Between Host and Virtual Machine

In this hands-on lab, I manually configured a subnet and set static IP addresses on both my physical (host) machine and a virtual Ubuntu machine. The goal was to ensure both systems were in the same subnet and able to communicate using basic network tools.

---

## 🧠 Subnet Configuration

### Host (Windows)

- **IP Address:** `192.168.1.2`
- **Subnet Mask:** `255.255.255.192` (CIDR: `/26`)
- **Default Gateway:** `192.168.1.1`
- **DNS Servers:** `1.1.1.1` and `1.0.0.1`

- ### 💻 Host IP Configuration (Windows)
![Host IP Settings]((https://github.com/user-attachments/assets/32292c3f-ad3b-4859-afa3-bdc8311294fb)
)

A `/26` subnet breaks a Class C network into **4 subnets**, each with:
- 62 usable IP addresses
- 1 network ID
- 1 broadcast address

---

## 🐧 Virtual Machine (Ubuntu in VirtualBox)

I launched an Ubuntu virtual machine and manually assigned it a static IP from the same subnet as the host:

- **IP Address:** `192.168.1.4/26`
### 🐧 Ubuntu VM IP Assignment
![Ubuntu IP Info](https://github.com/LyatifM/vm-subnetting-lab/blob/main/Screenshot%202025-06-06%20195925.png?raw=true)

### Commands used to change my ip and subnet on Ubuntu:
```bash
sudo ip addr add 192.168.1.3/26 dev enp0s3 <-- name of my network interface

ip a <-- to find out yours
```

---

## ✅ Connectivity Test

Since both the host and the VM are on the same subnet, they can communicate directly.

I successfully ran a **ping** from the VM to the host (`192.168.1.2`) and got replies, confirming proper configuration.
### 📶 Ping Success from VM to Host
![Ping Test]([img/ping-tests.png](https://github.com/LyatifM/vm-subnetting-lab/blob/main/Screenshot%202025-06-06%20202305.png?raw=true))

---

## 📸 Screenshots

---

## 🧠 What This Demonstrates

- How to manually assign static IPs on both Windows and Linux
- How to calculate and apply a `/26` subnet
- Real-world confirmation that devices in the same subnet can directly communicate
- Strengthening networking fundamentals through hands-on lab work

---

## 📍 Why I’m Doing This?

As part of my transition into IT, I'm building a solid base of practical knowledge by setting up and troubleshooting networks manually. Labs like this help turn theory into real, working understanding.
