
---
## Passive Recon - 

---
### 1. DNS Lookup Utility `host` Tool 

```
whatis host
```

	Tool used to find IP address to the domain name 

```
host hackersploit.org
```

---
### 2. `robots.txt`  & `sitemap.xml` file 

	 this text file tells information about what endpoints are indexed or allowed for crawlling by search engines like google, duck-duckGo, bing, etc.

- Crawling : Web crawling, also known as web spidering or web scraping, is a process where automated programs, called bots or spiders, systematically browse the internet to gather information from websites.

![[Pasted image 20250228144815.png]]

![[Pasted image 20250228145319.png]]

- usage : 
```
< URL > /robots.txt
```

```
< URL > /sitemap.xml
```

---
### 3.  `BuiltWith` and `Wapplayzer` 

![[Pasted image 20250228145800.png]]


![[Pasted image 20250228145828.png]]

---
### 4.  `Whatweb` Tool 

![[Pasted image 20250228150420.png]]

- usage : 

```
whatweb hackersploit.org 
```

---
### 5.  To Download entire website `httrack` tool.

![[Pasted image 20250228150729.png]]

	To install this tool in kali linux 

```
apt install webhttrack
```

![[Pasted image 20250228154340.png]]

	 we can use to this tool to download all information about the webstite 

![[Pasted image 20250228154451.png]]

---
### 6.  `Whois` Tool for gathering information about the website

- GUI - https://who.is/ 

```
whois hackersploit.org 
```

Target : https://digi.ninja/projects/zonetransferme.php

```
whois zonetransfer.me
```

Gathers Information about websites - 
- Register
- Mail's 
- IANA ID 
- Addresses 

![[Pasted image 20250228155029.png]]

---
### 7.  `Netcraft` Website 

	- link : https://sitereport.netcraft.com/

![[Pasted image 20250228160703.png]]

![[Pasted image 20250228160724.png]]

---
### 8.  `DNSrecon` tool  

	- Link : https://www.kali.org/tools/dnsrecon/

![[Pasted image 20250228161116.png]]

```
dnsrecon -d hackersploit.org 
```

```
dnsrecon -d zonetransfer.me 
```

```
dnsrecon -d zonetransfer.me -t axfr
```

| **Record** | **Description**              | **Pentesting Use**           |
| ---------- | ---------------------------- | ---------------------------- |
| **A**      | Domain → IPv4                | Find target's IP             |
| **AAAA**   | Domain → IPv6                | IPv6 recon                   |
| **CNAME**  | Alias for a domain           | Detect hidden infrastructure |
| **MX**     | Mail servers                 | Email spoofing, phishing     |
| **TXT**    | Text data (SPF, DKIM, DMARC) | Check email security flaws   |
| **NS**     | Name servers                 | Identify DNS infrastructure  |
| **SOA**    | Domain admin info            | Find internal details        |
| **PTR**    | Reverse DNS (IP → Domain)    | Identify hosts from IPs      |
| **SRV**    | Service & port info          | Expose running services      |
| **CAA**    | SSL/TLS certificate policy   | Check for misconfigurations  |

---
### 9.  `Sublist3r` Tool 

tool designed to enumerate subdomains of websites

Link : https://github.com/aboul3la/Sublist3r

```
apt install sublist3r
```

```
sublist3r -d hackersploit.org 
```

```
sublist3r -d hackersploit.org -e yahoo,google
```

```
sublist3r -d ine.com
```

| Short Form | Long Form    | Description                                             |
| ---------- | ------------ | ------------------------------------------------------- |
| -d         | --domain     | Domain name to enumerate subdomains of                  |
| -b         | --bruteforce | Enable the subbrute bruteforce module                   |
| -p         | --ports      | Scan the found subdomains against specific tcp ports    |
| -v         | --verbose    | Enable the verbose mode and display results in realtime |
| -t         | --threads    | Number of threads to use for subbrute bruteforce        |
| -e         | --engines    | Specify a comma-separated list of search engines        |
| -o         | --output     | Save the results to text file                           |
| -h         | --help       | show the help message and exit                          |

---
### 10. Google Dorks 

- `site:`  
```
site:tesla.com
site:*.tesla.com
site:tesla.com employees
```

- `inurl:`
```
 site:tesla.com inurl:admin
 site:*.tesla.com inurl:admin
 site:tesla.com inurl:forum
```

- `filetype:`
```
site:tesla.com filetype:pdf 

```

- `intitle:index of`
```
intitle:index of 
```

- `cache:`
```
cache:tesla.com
```

- `inurl:`
```
inurl:auth_user_file.txt
inurl:password.txt
inurl:wp-config.bak
```

```
site:gov.* ""index of *.csv
site:gov.* "index of" *.csv passwords
```

- username OSINT
```
"John Doe" site:linkedin.com
"John Doe" site:twitter.com
"John Doe" email OR phone
"John Doe" filetype:pdf OR filetype:doc
```

---
### 11. `Waybackmachine` Web Archive 

Link : https://web.archive.org/ 

---
### 12. `theHarvester` Tool 

link : https://github.com/laramies/theHarvester

```
sudo apt install theharvester
```

```
theHarvester -d tesla.com 
```

```
theHarvester -d tesla.com -b google,linkedin
```

```
theHarvester -d tesla.com -b all
```

---
### 13. Leak Password Databases

Link : https://haveibeenpwned.com/ 

---
### 14. `Wafw00f` Tool 

link : https://github.com/EnableSecurity/wafw00f 

```
wafw00f tesla.com
```

```
wafw00f zonetransfer.me
```

```
wafw00f https://hackertube.net -a
```

---
### 15. Email & Username OSINT 

- Link : https://phonebook.cz/
- Link : https://dehashed.com/
- Link : https://whatsmyname.app/

---
### 16. Information gathering website 

- Link : https://centralops.net/
- Link : https://dnslytics.com/
- Link : https://www.virustotal.com/
- Link : https://viewdns.info/
- Link : https://crt.sh/

---
### 17. Shodan  & Censys

- Link : https://www.shodan.io/

```r
# API KEYS 
1. Jvt0B5uZIDPJ5pbCqMo12CqD7pdnMSEd
2. 17xz7MYEBoXLPoi8RdqbgkPwTV2T2H0y
3. fW9K4luEx65RscfUiPDakiqp15jiK5f6
4. pHHlgpFt8Ka3Stb5UlTxcaEwciOeF2QM

```
- Link : https://search.censys.io/

`city:`
```
city:Mumbai rdp
city:mumbai remote desktop
```

- CLI COMMANDS
```r

# Search for ADB devices (port 5555)
shodan search "port:5555" --fields ip_str,port,org,hostnames,country --limit 50

# Search for RDP servers (port 3389)
shodan search "port:3389" --fields ip_str,port,org,hostnames,country --limit 50

# Search for FTP servers with anonymous login
shodan search "ftp anonymous" --fields ip_str,port,org,hostnames,country --limit 50

# Search for SMB shares
shodan search "smb" --fields ip_str,port,org,hostnames,country --limit 50

# Search for webcams or MJPEG/RTSP streams
shodan search "webcamxp OR mjpg OR netcam OR port:554" --fields ip_str,port,org,hostnames,country --limit 50

# Search for IoT devices exposing HTTP/HTTPS services
shodan search "port:80 OR port:443" --fields ip_str,port,org,hostnames,country --limit 50

# Search devices under a specific ASN (replace ASXXXX with your ASN)
shodan search "asn:AS15169" --fields ip_str,port,org,hostnames,country --limit 50

# Search devices in a specific network range
shodan search "net:192.168.1.0/24" --fields ip_str,port,org,hostnames,country --limit 50

# Search for email addresses exposed on devices or services
shodan search "email" --fields ip_str,port,org,hostnames,country,data --limit 50

# Search for phone numbers exposed on devices or web services
shodan search "phone" --fields ip_str,port,org,hostnames,country,data --limit 50

# Search for exposed API keys, tokens, or credentials
shodan search "api key OR password OR token" --fields ip_str,port,org,hostnames,country,data --limit 50

# Search for exposed MongoDB, Elasticsearch, Redis, or SQL databases
shodan search "product:MongoDB OR product:Elasticsearch OR port:6379 OR port:27017" --fields ip_str,port,org,hostnames,country --limit 50

# Get detailed info about a specific IP
shodan host 8.8.8.8

# Search Users 
shodan search "author:John Doe"

# Find hosts vulnerable to Log4Shell
shodan search "vuln:CVE-2021-44228" --fields ip_str,port,org,hostnames,country

# Exposed SCADA servers
shodan search "port:502 OR port:102" --fields ip_str,port,org,hostnames,country

# Search for Siemens PLCs
shodan search "product:Siemens S7" --fields ip_str,port,org,hostnames,country

# Satellite and Aerospace Equipment
shodan search "satellite telemetry" --fields ip_str,port,org,hostnames,country

# Cloud S3 buckets 
shodan search "S3 OR bucket OR storage.googleapis.com" --fields ip_str,port,org,hostnames,country

# Honepots search 
shodan search "S3 OR bucket OR storage.googleapis.com" --fields ip_str,port,org,hostnames,country

# Search for default router logins
shodan search "title:admin" --fields ip_str,port,org,hostnames,country

# Public Infra and Cameras
shodan search "city camera OR traffic sensor" --fields ip_str,port,org,hostnames,country

# Bitcoin and Cryptocurrency nodes 
shodan search "port:8333 bitcoin" --fields ip_str,port,org,hostnames,country

# Search for web servers hosting course PDFs
shodan search "index of pdf cyber security course" --fields ip_str,port,org,hostnames,country,data --limit 50

# Search for public XMPP chat servers
shodan search "port:5222 xmpp" --fields ip_str,port,org,hostnames,country,data

# Search for Matrix chat servers
shodan search "port:8448 matrix" --fields ip_str,port,org,hostnames,country,data

# Search for HTTP headers containing cookies
shodan search "Set-Cookie" --fields ip_str,port,org,hostnames,country,data --limit 50

# Filter HTTP headers for cookies
shodan search "hostname:example.com Set-Cookie" --fields ip_str,port,org,hostnames,country,data

shodan search "hostname:netflix.com Set-Cookie" --fields ip_str,port,hostnames,data --limit 50 --csv > netflix_cookies.csv

# KEYS 
shodan search "api_key" hostname:yourlab.example.com
shodan search "Authorization: Bearer" hostname:lab.example.com
shodan search "/dev/api" hostname:127.0.0.1
shodan search "aws_access_key_id" hostname:lab.example.com
shodan search "secret_key" hostname:lab.example.com
shodan search "config.yaml" hostname:lab.example.com
```

- Shodan scan
```
shodan scan submit 8.8.8.8
```

---
### 18. Image OSINT 

-  Link : https://pimeyes.com/en

---
### 19. `subfinder` tool 

```
subfinder -d tesla.com
```

---
### 20. `Amass` Tool
 
```
amass enum -d tesla.com
```


---
### 21. `GEO LOCATION` 

1. Hackers often use **link tracking** tools—like `Grabify or bespoke IP-grabber` scripts—to record your IP address when you click a link. Once clicked, the link directs you through their server, logging your IP and sometimes device info and location, which they then analyze.
	- https://grabify.link/
	- https://grabify.org/


2. When Hackers get IP Address about target they gather information about target form various website 

```
curl ipinfo.io/<IP address>
```

![[Pasted image 20250701132510.png]]

```
curl ip-api.com/json/<IP ADDRESS>
```

![[Pasted image 20250701132704.png]]

3. OSINT - `https://osintframework.com/` Now hackers try to gather information from what they got from search engines like `shodan`
```powershell
asn:ASxxxx
org:"Example Org Name"
net:203.0.113.0/24
port:22 openssh
port:445 "Authentication Disabled"

# You can combine multiple dorks 
asn:AS12345 org:"ACME Ltd" net:203.0.113.0/24

```

---
# 22. Ph No Information gathering `PhoneInfoga`
`PhoneInfoga` is one of the most advanced tools to scan international phone numbers. It allows you to first gather basic information such as country, area, carrier and line type, then use various techniques to try to find the VoIP provider or identify the owner.

- https://github.com/sundowndev/phoneinfoga
- https://sundowndev.github.io/phoneinfoga/getting-started/install/

```bash
bash <( curl -sSL https://raw.githubusercontent.com/sundowndev/phoneinfoga/master/support/scripts/install )
```

- Install globally 
```
sudo install ./phoneinfoga /usr/local/bin/phoneinfoga
```

`USEAGE` --> 
1. CLI 
```
phoneinfoga scan -n +1 123-456-7890
phoneinfoga scan -n "+1 123-456-7890"
```

2. GUI 
```
phoneinfoga serve -p 8080
```

> You can also integrate API key for more information gathering 


```bash
phoneinfoga scan -n +11234567890 --env-file=mykeys.env  //add api keys in this files 

mykeys.env
		NUMVERIFY_API_KEY="PASTE_YOUR_NUMVERIFY_KEY"
		GOOGLE_API_KEY="PASTE_YOUR_GOOGLE_KEY"
		GOOGLECSE_CX="PASTE_YOUR_SEARCH_ENGINE_CX"



OR 

NUMVERIFY_API_KEY=abc123 GOOGLE_API_KEY=xyz456 phoneinfoga scan -n +11234567890

# YOU can get API form here `https://apilayer.com/marketplace`
# Just search "number verification api" 
```

---
# 23. security headers by `snyk`

- Link - https://securityheaders.com/

![[Pasted image 20250706134115.png]]

---
## Active Recon -

---
### 1. DNS Zone Transfer 

	- DNS : Domain Name Server is an protocol used to resolve IP address, hostname to its IP addresses
	- DNS Intorogation can provide information like IP address to particular server and records of Nameserver or Mail servers 
	- DNS Records :

| **Record** | **Description**              | **Pentesting Use**           |
| ---------- | ---------------------------- | ---------------------------- |
| **A**      | Domain → IPv4                | Find target's IP             |
| **AAAA**   | Domain → IPv6                | IPv6 recon                   |
| **CNAME**  | Alias for a domain           | Detect hidden infrastructure |
| **MX**     | Mail servers                 | Email spoofing, phishing     |
| **TXT**    | Text data (SPF, DKIM, DMARC) | Check email security flaws   |
| **NS**     | Name servers                 | Identify DNS infrastructure  |
| **SOA**    | Domain admin info            | Find internal details        |
| **PTR**    | Reverse DNS (IP → Domain)    | Identify hosts from IPs      |
| **SRV**    | Service & port info          | Expose running services      |
| **CAA**    | SSL/TLS certificate policy   | Check for misconfigurations  |

	- DNS ZONE TRANSFER ATTACK --> 

1. DNS server admins may wants to copy or `transfer` zone files from one DNS Server to another. This process is known as zone transfer.
2. If it is left misconfigured, this functionality can be abused by attackers to copy the `zone file` from primary DNS server to another DNS Server.
3. DNS zone transfer can provide penetration tester view of an organization's network layout
4. Internal Network address can be found on an Organizations DNS Servers.

```
dnsenum zonetransfer.me
```

```
dig axfr @nsztm1.digi.ninja zonetransfer.me
```

```
fierce -dns zonetransfer.me
```

---
### 2. `arping` tool

```
arping 192.168.1.1 -c 3
```

```bash
for ip in {1..254}; do arping -c 1 -i eth0 192.168.236.$ip; done
```

---
### 3. `netdiscover` Tool 


```
netdiscover -p
```

- `wireshark` --> `arp.proto.type`

```
netdiscover -i eth0 -r 192.168.1.0/24
```

---
### 4. `Nmap` Network Scanner 

- `wireshark` - `ip.addr==target`

` Host Discovery` `-sn` : Tells Nmap not to do port scan after Host discovery.

```
nmap -sn 192.168.10.0/24
```

---





