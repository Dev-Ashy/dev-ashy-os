# Dev-Ashy OS Security Tools

Dev-Ashy OS includes a comprehensive set of security tools for penetration testing, vulnerability assessment, and security research.

## Network Scanning

### Nmap

```bash
# Basic scan
nmap target.com

# Full scan
nmap -A -T4 target.com

# Vulnerability scan
nmap --script vuln target.com
```

### Netcat

```bash
# Listen on port
nc -lvp 4444

# Connect to host
nc target.com 80
```

## Web Security

### Nikto

```bash
# Scan web server
nikto -h target.com
```

### SQLMap

```bash
# Test URL
sqlmap -u "http://target.com/page?id=1"

# Test with authentication
sqlmap -u "http://target.com/login" --data="user=admin&pass=pass"
```

### Dirb

```bash
# Brute force directories
dirb http://target.com /usr/share/wordlists/dirb/common.txt
```

### Gobuster

```bash
# Brute force directories
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt
```

## Password Cracking

### John the Ripper

```bash
# Crack password file
john passwords.txt

# Show cracked passwords
john --show passwords.txt
```

### Hashcat

```bash
# Crack MD5 hash
hashcat -m 0 hash.txt wordlist.txt

# Crack SHA256 hash
hashcat -m 1400 hash.txt wordlist.txt
```

### Hydra

```bash
# SSH brute force
hydra -l root -P wordlist.txt ssh://target.com

# FTP brute force
hydra -l admin -P wordlist.txt ftp://target.com
```

## Wireless Security

### Aircrack-ng

```bash
# Start monitor mode
airmon-ng start wlan0

# Capture packets
airodump-ng wlan0mon

# Crack WPA
aircrack-ng -w wordlist.txt -b BSSID capture.cap
```

## Packet Analysis

### Wireshark

```bash
# Start Wireshark
wireshark

# Capture from command line
tshark -i eth0 -w capture.pcap
```

### TCPDump

```bash
# Capture all traffic
tcpdump -i eth0 -w capture.pcap

# Capture specific port
tcpdump -i eth0 port 80
```

## Reverse Engineering

### Radare2

```bash
# Analyze binary
r2 -A ./binary

# Disassemble
r2 -A -c "pd 20" ./binary
```

### Ghidra

```bash
# Start Ghidra
ghidra
```

## Steganography

### Steghide

```bash
# Hide file
steghide embed -cf image.jpg -ef secret.txt

# Extract file
steghide extract -sf image.jpg
```

## Firmware Analysis

### Binwalk

```bash
# Analyze firmware
binwalk firmware.bin

# Extract firmware
binwalk -e firmware.bin
```

## Vulnerability Scanning

### Metasploit

```bash
# Start Metasploit
msfconsole

# Search exploit
search eternalblue

# Use exploit
use exploit/windows/smb/ms17_010_eternalblue
```

## Important Notes

1. **Only use these tools on systems you own or have explicit permission to test**
2. **Unauthorized access to computer systems is illegal**
3. **Use these tools for educational and authorized security testing purposes only**
4. **Follow all applicable laws and regulations**

## Next Steps

- [Installation](installation.md) — Install Dev-Ashy OS
- [AI Tools](ai-tools.md) — Set up AI tools
- [Building](building.md) — Build from source
