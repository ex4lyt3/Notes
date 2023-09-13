# eJPT Notes

## Section 1: Assessment Methologies

### Passive Information Gathering

- Linux Commands
  - `host` - linux command used for checking IP address of website
  - `whatweb` - linux commnad (preinstalled on kali) used for duscovering web technologies that are used in a website
  - `dnsrecon` - linux command (preinstalled on kali) used for revealing dns information (in the form of dns records) of websites
- Web Files
  - `robots.txt` - web file that prevents web crawlers from indexing specific directories mentioned in the `disallow:` section
  - `sitemap.xml` - web file that provides engines an organised way to structure the website, provides webpages that can be publicly accessed on search engines
- Web Extensions
  - **Built With** - web extension that shows the website's details
  - **WAPPALYZER** - another web extension that shows what web technologies are used in a website
- Information Gathering Tools
  - **WebHTTRack** - tool that allows you to copy a website online into a local directory
  - **WHOIS** - query and response protocol that shows domain name availability or to discover domain information
  - **NetCraft** - website that provides a ton of information on websites
  - **DNS Dumpster** - similiar to `dnsrecon` but more organised
  - **WAFW00F** - web application firewall fingerprinting tool `wafw00f`
  - **Sublist3r** - tool that performs enumerates subdomains of websites using OSINT `sublist3r`
  - **Wayback Machine** - tool that shows how websites looked like in the past
  - **Google Hacking Database** - exploit-db page that shows interesting google dorks that reveal information
  - **The Harvester** - tool that gathers email addresses, names, addresses, IPs and URLs using multiple public data sources `theharvester`
- Google Dorks
  - `site:` - limit all results specific to that site
    - `site: *.site.com` - limit all results specific to the site's subdomains, where * means anything (wildcard character)
  - `inurl:` - limit all results that contain that in the url
  - `intitle` - limit all results that contain that in the title
  - `filetype:` - limit all results that are that specific filetype
  - `cache:` - loads the website information stored in your cache
- Leaked Password Databases
  - **haveibeenpwned.com** - website that allows users to check if their email or phone has been in a data breach - linked to theharvester where the information previous gathered (for example email addresses) can be used in this website to check if they have been in a data breach where their passwords have been leaked

### Active Informaiton Gathering

- DNS Zone Transfers
  - What is DNS?
    - Domain Name System is a protocol that is used to resolve domain names/hostnames into IP addresses. 
    - A DNS server is like a telephone directory that contains domain names and their corresponding IP addresses
    - A plethora of public DNS servers have been se up by companies Cloudflare and Google. These DNS servers contain the records of almost all domains on the internet.
  - DNS Records
    - A - Resolves a hostname or domain to an IPv4 address
    - AAAA - Resolves a hostname or domain to an IPv6 address
    - NS - Reference tp the domains nameserver
    - MX - Resolves a domain to a mail server
    - CNAME - Used for domain aliases
    - TXT - Text record
    - HINEO - Host Information
    - SOA - Domain authority
    - SRV - Service records
    - PTR - Resolves an IP address to a hostname
  - DNS Interrogation
    - DNS interrogation is the process of enumerating DNS records for a specific domain
    - The objective of DNS interrogation is to probe a DNS server to provide us with DNS records for a specific domain
    - This process can provide with important information like the IP address of a domain, subdomains, mail server addresses etc.
    - This process can provide with improtant information like the IP address of a domain, subdomains, mal server addresses
  - DNS Zone Transfer
    - Zone files contain DNS information
    - In certain cases DNS server admins may want to copy or transfer zone files from one DNS server to another. This is known as a zone transfer.
    - If misconfigured and left unsecured, this functionality can be abused by attackers to copy the zone file from the primary DNS server to another DNS server
    - A DNS Zone transfer can provide penetration testers with a hollistic view of an organisation's network layout
    - Furthermore, in certain cases, internal network addresses may be found on an organisation's DNS servers.
  - `dnsenum`
    - Tool that performs both passive and active DNS reconnaissance (and tries to automatically perform a DNS zone transfer)
  - `dig`
    - dns lookup utility
  - `fierce`
    - A semi-lightweight scanner that helps locate non-contiguous IP space and hostnames against specificed domains.
  - "Local DNS Server"
    - In linux systems, the `/etc/hosts` file locally maps domain names to IP addreses in the system itself.
  - Host Discovery with `nmap`
    - `sudo nmap -sn 192.168.20.0/24` - scans all IP addresses in the range (in this case, its `192.168.20.0/24`, 192.168.20.0-192.168.20.255, where 192.168.20.0 is the subnet mask)
  - Port Discovery with `nmap`
    - `nmap` - performs default nmap scan - SYN scan on thousand most frequently used ports
      - `nmap -Pn` - avoid checking if host is online
      - `nmap -p-` - check all 65,535 ports
      - `nmap -p 80,443` - select specific ports to scan (in this example, port 80 and 443)
      - `nmap -p 10-443` - select port range to scan (in this example, port 10 to 443)
      - `nmap -F` - perform fast scan
      - `nmap -sU` - perform **UDP** scan
      - `nmap -v` - increase verbosity of the scan, provide more details on the scan
      - `nmap -sC` - run a list of nmap scripts to enumerate more information from these open ports
      - `nmap -T5` - adjust timing template to 5 (controls how fast nmap scans from a range of 0 to 5 )
  - Service Discovery with `nmap`
    - `nmap -sV` - perform service version discovery (on the ports)
