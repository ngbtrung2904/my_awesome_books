# NMAP Commands

- Scan all hosts in a network: `sudo nmap -sP <host>/numbits`
```bash
nbt@tower7810:~$ sudo nmap -sP 192.168.1.1/24
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-08-02 17:06 +07
Nmap scan report for 192.168.1.1 (192.168.1.1)
Host is up (0.011s latency).
Nmap scan report for 192.168.1.3 (192.168.1.3)
Host is up (0.0098s latency).
Nmap scan report for 192.168.1.188 (192.168.1.188)
Host is up (0.028s latency).
Nmap done: 256 IP addresses (3 hosts up) scanned in 3.99 seconds
```

- Check for open ports of all devices in network
```bash
nbt@tower7810:~$ sudo nmap -p- -sS -T4 192.168.68.0/24
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-08-02 17:40 +07
Nmap scan report for 192.168.68.1 (192.168.68.1)
Host is up (0.0054s latency).
Not shown: 65530 closed tcp ports (reset)
PORT      STATE SERVICE
53/tcp    open  domain
80/tcp    open  http
443/tcp   open  https
1900/tcp  open  upnp
20001/tcp open  microsan
MAC Address: 14:EB:B6:C7:28:DC (TP-Link Limited)

Nmap scan report for 192.168.68.119 (192.168.68.119)
Host is up (0.0000050s latency).
Not shown: 65532 closed tcp ports (reset)
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
8889/tcp open  ddi-tcp-2

Nmap done: 256 IP addresses (2 hosts up) scanned in 66.87 seconds
```

- Check open ports of on specific device
```bash
nbt@tower7810:~$ sudo nmap -p- -sS -T4 192.168.68.119
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-08-02 17:41 +07
Nmap scan report for 192.168.68.119 (192.168.68.119)
Host is up (0.0000050s latency).
Not shown: 65532 closed tcp ports (reset)
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
8889/tcp open  ddi-tcp-2

Nmap done: 1 IP address (1 host up) scanned in 0.74 seconds
```