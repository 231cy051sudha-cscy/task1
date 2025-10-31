# task1
1. install nmap
command
# first want to update 
sudo apt update
#if already installed 
sudo --version
# If not installed, install it
sudo apt install nmap -y
# after installation 

2. Find your local IP range
 ip addr show - to find ip range

3. Run: nmap -sS  10.0.2.0/24 to perform TCP SYN scan
# Perform TCP SYN scan on your local network
sudo nmap -sS 10.0.2.0/24
* sudo - Administrative privileges required for SYN scans
* nmap - The scanning tool
* -sS - TCP SYN scan (stealth scan, doesn't complete TCP handshake)
* 10.0.2.0/24 - Your entire local network range

4. Note down IP addresses and open ports found.
PORT      STATE SERVICE
21/tcp    open  ftp
80/tcp    open  http
135/tcp   open  msrpc
443/tcp   open  https
445/tcp   open  microsoft-ds
1521/tcp  open  oracle
3306/tcp  open  mysql
5357/tcp  open  wsdapi
5500/tcp  open  hotline
16992/tcp open  amt-soap-http
sudo nmap -sS -sV -p 21,80,135,443,445,1521,3306,5357,16992 10.0.2.2
i. -sV
Service/version detection. After finding an open port nmap will probe the service (send protocol-specific requests) to try to determine the service name and version.
ii. -p tells nmap which ports to scan. The comma-separated list means “scan only these TCP ports” (rather than the default top 1,000 or -p- for all 65535).
21 — FTP (File Transfer Protocol) control port.
80 — HTTP (web) unencrypted.
135 — Microsoft RPC (Remote Procedure Call) / endpoint mapper.
443 — HTTPS (HTTP over TLS).
445 — Microsoft-DS / SMB (file sharing over TCP).
1521 — Oracle Database listener (default).
3306 — MySQL / MariaDB server.
5357 — Web Services for Devices (WSD) / HTTP-based device services (sometimes used for printer discovery).
16992 — Intel AMT (Active Management Technology) web interface (commonly used for out-of-band management).
   
   


