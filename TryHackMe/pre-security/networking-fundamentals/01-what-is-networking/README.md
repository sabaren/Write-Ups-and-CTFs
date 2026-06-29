# TryHackMe: What is Networking? Writeup
**Room Link:** [What is Networking?](https://tryhackme.com/room/whatisnetworking)
**Objective:** Comprehend the foundational elements of computing networks, examine how devices are uniquely identified via IP and MAC addresses, and utilize essential diagnostic utilities like Ping.

---

## 1. Introduction to Networking & The Internet
A network is defined as a collection of two or more connected computing devices that communicate using established sets of rules (protocols). 

### Network Classifications
* **Private Network:** An internal network configuration where devices utilize private IP addresses to communicate directly with one another locally.
* **Public Network (The Internet):** A massive global network connecting countless smaller private networks together. External data transmission across the public internet is routed via public IP addresses assigned by an Internet Service Provider (ISP).

---

## 2. Device Identification Protocols
To ensure structured communication, every host on a network is assigned two primary forms of identification: a logical address (IP) and a physical address (MAC).

### IP Addresses (IPv4 vs. IPv6)
An Internet Protocol (IP) address serves as a temporary logical identifier for a host on a network. 
* **IPv4:** Composed of four decimal sections known as **octets** separated by periods (e.g., `192.168.1.1`). It uses a 32-bit scheme limiting the total pool to 4.29 billion addresses, causing an international supply shortage.
* **IPv6:** Developed to mitigate IPv4 exhaustion. It utilizes a 128-bit scheme supporting over 340 trillion addresses and features enhanced routing efficiency.

### MAC Addresses & Spoofing Risks
A Media Access Control (MAC) address is a permanent, 128-bit (12-character) hexadecimal physical serial number burned into a device’s Network Interface Card (NIC) at the factory. 

Because many networks rely on MAC filters to authorize trusted devices (like administrator access or guest Wi-Fi billing gateways), they are highly susceptible to **MAC Spoofing**. This occurs when an attacker alters their local configuration to mirror an authorized device's physical address, successfully bypassing perimeter access controls.

### Practical Lab: Bypassing Captive Portal Filters via MAC Spoofing
A simulation of a restricted hotel captive portal gateway was conducted. A commercial router blocked packets from an unpaid host (Bob) while permitting traffic from a paid host (Alice). 

By analyzing the network and spoofing Bob's local hardware configuration to match Alice's valid MAC address (`00:12:32:2F:33:39`), the router gateway was deceived into authorizing the connection. This allowed arbitrary access to the target web resource.

Refer to the image below for the successful bypass and flag generation.

![MAC Spoofing Success](tdo.png)

---

## 3. Network Diagnostics with Ping (ICMP)
`Ping` is a fundamental command-line utility used to test host reachability and network performance. It utilizes the **Internet Control Message Protocol (ICMP)** to transmit `Echo Request` packets to a target destination and measures the round-trip time required to receive an `Echo Reply`.

### Practical Lab: Pinging a Remote Target
The utility was executed against a public DNS server to test network reachability and connectivity metrics.

```bash
user@thm:~$ ping -c 4 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data
64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=9.47 ms
64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=9.36 ms
64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=7.79 ms
64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=7.73 ms
--- 8.8.8.8 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 4006ms
rtt min/avg/max/mdev = 8.132/9.428/10.957/1.057 ms
Flag: THM{I_PINGED_THE_SERVER}
