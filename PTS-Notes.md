# eJPT Notes

## Section 1: Assessment Methologies

### Passive Information Gathering

- Linux Commands
  - `host` - linux command used for checking IP address of website
  - `whatweb` - linux commnad (preinstalled on kali) used for duscovering web technologies that are used in a website
  - `dnsrecon` - linux command (preinstalled on kali) used for revealing dns information (in the form of dns records) of websites
    - A - IPv4 address
    - AAAA - IPv6 address
    - MX - Mail server (email service)
    - NS - Name server
    - TXT - custom record with custom text (used to track a website's analytics with Google)
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
