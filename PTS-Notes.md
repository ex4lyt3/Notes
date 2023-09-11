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
  - **WHOIS** query and response protocol that shows domain name availability or to discover domain information
  - **NetCraft** - website that provides a ton of information on websites
  - **DNS Dumpster** - similiar to `dnsrecon` but more organised
