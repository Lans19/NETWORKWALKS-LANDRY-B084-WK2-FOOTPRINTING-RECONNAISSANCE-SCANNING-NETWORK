# NETWORKWALKS-LANDRY-B084-WK2-FOOTPRINTING-RECONNAISSANCE-SCANNING-NETWORK

# 🛡️ Penetration Testing Report  
## 🔍 Footprinting & Network Scanning Phases  
**WK2-PM-FINAL | Cybersecurity | Networkwalks**

**Pentester Name:** Landry Kasapato Semilwo  
**Program/Batch:** Cybersecurity  
**Date:** 12 November 2026  

| Module | Title | Phase Covered |
|---|---|---|
| WK2-PM1 | Multiple Kali Tools | Reconnaissance and Footprinting |
| WK2-PM2 | GHDB (Google Hacking Database) | Reconnaissance and Footprinting |
| WK2-PM3 | Maltego | Reconnaissance and Footprinting |
| WK2-PM4 | theHarvester | Reconnaissance and Footprinting |
| WK2-PM5 | Zenmap Scanning | Scanning and Network Discovery |

**Client/Target:**  
1. Networkwalks (written permission already secured)  
2. My own local LAN network  

**Permission secured from client:** Yes  

**Phases covered:**  
- Phase 1: Reconnaissance and Footprinting  
- Phase 2: Scanning and Network Discovery  
- Phases 3–5: In progress  

## ⚠️ 1. Liability Disclaimer

I performed these activities only on systems and devices for which I had secured written permission, or on devices and systems that I own myself. All materials in this report are for educational and research purposes only.

Do not use any information in this report to break the law. The instructor, authors, and Networkwalks are not responsible for how this knowledge is used. Every action you take is your own responsibility. Misuse may lead to criminal charges, fines, loss of employment, and a permanent record. In most countries, unauthorised access is a crime even if no damage is caused.

## 📘 2. Introduction

This report covers the Week 2 practical activities completed as part of the Cybersecurity and Ethical Hacking internship at Networkwalks. It documents five modules: **WK2-PM1 (Multiple Kali Tools), WK2-PM2 (GHDB), WK2-PM3 (Maltego), WK2-PM4 (theHarvester), and WK2-PM5 (Zenmap Scanning)**.

The first four modules focused on reconnaissance and footprinting, while the final module focused on scanning and network discovery. Together, these activities demonstrate how a security professional can gather publicly available information about a target and identify active devices on a local network.

All footprinting activities were performed against the authorised target, `networkwalks.com`, using Kali Linux. Maltego was used on a Windows computer, while Zenmap was used to scan the tester’s own local network. No exploitation or vulnerability validation was performed.

## 🧰 3. Tools Used

| Tool | Purpose |
|---|---|
| Kali Linux | Primary operating system used for reconnaissance and footprinting activities. |
| Windows | Used for Maltego and Zenmap activities. |
| WHOIS | Retrieves publicly available domain registration information, including registrar details and name servers. |
| WhatWeb | Identifies web technologies, including the web server, CMS, plugins, and IP address. |
| Nslookup | Resolves a domain name to its IP address using DNS. |
| Curl | Retrieves and inspects HTTP response headers. |
| Wafw00f | Detects whether a Web Application Firewall (WAF) protects a website. |
| DNSRecon | Enumerates DNS records, including NS, MX, SPF, TXT, and SRV records. |
| Google Hacking Database (GHDB) | Provides search operators and dorks used to identify publicly exposed information. |
| Maltego | Performs open-source intelligence (OSINT) analysis and maps relationships between domains, email addresses, and infrastructure. |
| theHarvester | Collects publicly available information such as email addresses, hosts, and subdomains. |
| Zenmap (Nmap GUI) | Performs network discovery, identifies live hosts, and generates a network topology. |
| Windows Command Prompt | Used to identify the local IP address and network configuration. |

## 🧪 4. Activities Performed

### 🐧 4.1 WK2-PM1: Multiple Kali Tools

I performed reconnaissance against the authorised target, `networkwalks.com`, using WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, and DNSRecon. Each tool was used to collect a different type of publicly available information about the target domain.

First, I used WHOIS to obtain domain registration details and identify the domain’s name servers. The results showed that the domain was registered through GoDaddy and used HostGator name servers.

I then used WhatWeb to identify the technologies used by the website. The scan identified Apache as the web server, WordPress as the content management system, and WP Download Manager as a WordPress plugin. The website’s IP address was also identified as `192.232.216.135`.

Using Nslookup, I resolved the domain name to its IP address. The result confirmed that `networkwalks.com` resolved to `192.232.216.135`.

I used Curl with the `-I` option to inspect the HTTP response headers. This revealed information about the web server and exposed the WordPress REST API endpoint, `/wp-json/`.

Next, I used Wafw00f to determine whether a Web Application Firewall was protecting the website. The scan identified ModSecurity (SpiderLabs) as the WAF.

Finally, I used DNSRecon to enumerate DNS records. The results provided information about name servers, mail servers, SPF and TXT records, service records, and DNS software.

### 🔎 4.2 WK2-PM2: GHDB

I used the Google Hacking Database (GHDB) to identify publicly accessible information using Google search operators, also known as Google dorks. This activity demonstrated how search engines can expose sensitive or unintentionally public information.

#### 📷 Task 1: Find 10 live, exposed, and accessible security camera links

| No. | Link | Relevant Dork | Username / Password |
|---|---|---|---|
| 1 | http://109.233.191.130:8080/ | `intitle:"webcamXP" inurl:8080` | --- |
| 2 | http://99.114.240.169:8080/ | `intitle:"Webcam" inurl:WebCam.htm` | --- |
| 3 | http://220.254.144.208/ | `inurl:"CgiStart?page="` | --- |
| 4 | http://193.77.49.122/ | `intitle:"IP CAMERA Viewer" intext:"setting \| Client setting"` | --- |
| 5 | http://178.192.60.80:8888/ | `intitle:"yawcam" inurl:":8081"` | --- |
| 6 | http://178.142.207.0/ | `intitle:"webcamXP 5" -download` | --- |
| 7 | http://72.199.200.5:8080/ | `intext:"powered by webcamXP 5"` | --- |
| 8 | http://45.95.228.244/view/viewer_index.shtml?id=380 | `intitle:"live view" -axis 206w allintitle:liveapplet` | --- |
| 9 | http://100.37.240.26:93/ViewerFrame?Mode=Motion&Language=4 | `intitle:"Network Camera" inurl:ViewerFrame` | --- |
| 10 | http://80.152.138.183/ViewerFrame?Mode=Motion&Language=0 | `inurl:ViewerFrame?M0de=` | --- |

#### 📚 Task 2: Find 10 listings containing downloadable mathematics e-books in PDF format

| No. | Link | Relevant Dork | Username / Password |
|---|---|---|---|
| 1 | https://ies.ed.gov/sites/default/files/migrated/rel/regions/northwest/pdf/Foundational_Mathematical_Content_for_PK-5_Annotated_Bibliography.pdf | `intitle:index.of "parent directory" mathematics pdf` | --- |
| 2 | https://antinifizicari.wordpress.com/wp-content/uploads/2019/08/basic-mathematics-for-college-students-pdfdrive.com-.pdf | `intitle:"ebook" mathematics pdf` | --- |
| 3 | https://people.math.wisc.edu/~angenent/Free-Lecture-Notes/free221.pdf | `filetype:pdf "mathematics" OR "calculus" OR "algebra"` | --- |
| 4 | https://faculty.sites.iastate.edu/keinert/files/inline-files/math473.pdf | `site:.edu filetype:pdf "lecture notes" "mathematics"` | --- |
| 5 | https://textbookequity.org/Textbooks/Prealgebra.pdf | `"Creative Commons" "mathematics" "textbook" filetype:pdf` | --- |
| 6 | https://www.math.kent.edu/~mathweb/ebooks/10021/CMI.pdf | `inurl:open-textbooks "mathematics" filetype:pdf` | --- |
| 7 | https://www.istes.org/seeder/books/files/ba15f445541c378e7a39043f78309295.pdf | `filetype:pdf "mathematics" "CC BY" OR "CC BY-SA"` | --- |
| 8 | https://gcc.gnu.org/onlinedocs/gcc-10.3.0/libquadmath.pdf | `filetype:pdf "mathematics" "GNU Free Documentation License"` | --- |
| 9 | https://ocw.mit.edu/courses/6-042j-mathematics-for-computer-science-spring-2015/mit6_042js15_textbook.pdf | `site:ocw.mit.edu filetype:pdf "textbook" "mathematics"` | --- |
| 10 | https://education.giakonda.org.uk/Maths/math7.pdf | `intitle:"index of" "parent directory" "mathematics" pdf` | --- |

This activity showed that poorly configured devices, directories, and files can be indexed by search engines and discovered by attackers. Organisations should regularly review what information is publicly accessible online.

### 🕸️ 4.3 WK2-PM3: Maltego

I used Maltego to perform open-source intelligence (OSINT) analysis on the authorised target domain. Maltego was used to create a visual graph showing relationships between the domain and associated information.

I created a new graph and added `networkwalks.com` as the starting entity. I then used the available transforms to gather related information, including email addresses associated with the domain.

The Maltego graph identified `info@networkwalks.com` as an email address associated with the target domain. This demonstrated how OSINT tools can reveal contact information and help build a profile of an organisation’s online presence.

This activity showed the importance of controlling publicly available information, as email addresses and domain relationships can be used for reconnaissance, phishing awareness, and further investigation.

### 🌐 4.4 WK2-PM4: theHarvester

I used theHarvester to collect publicly available information about a target domain. The tool was used to search for information such as email addresses, hosts, subdomains, and IP addresses.

I first ran theHarvester against `microsoft.com` using the Baidu search engine with a limit of 1,000 results. The scan did not return any emails, hosts, people, or IP addresses.

I then ran theHarvester using the `all` option with a limit of 50 results. Some data sources could not be used because API keys were not configured, including BeVigil, Bitbucket, BufferOverrun, and BuiltWith.

This activity demonstrated that OSINT tools may return different results depending on the data sources and API keys available. It also showed the importance of configuring tools correctly before conducting reconnaissance.

### 🖥️ 4.5 WK2-PM5: Network Scanning with Zenmap

For the final activity, I used Zenmap to perform network discovery on my own local network. The purpose of the scan was to identify the local IP address and subnet, discover live hosts, collect IP and MAC address information, and create a network topology.

I first used the Windows `ipconfig` command to identify my local IP address and LAN subnet. I then entered the subnet into Zenmap and selected the **Ping Scan** profile to identify active hosts.

The scan used the following Nmap command:

```bash
nmap -sn 10.0.0.0/24
```

The scan identified four live hosts on the local network:

- `10.0.0.1`
- `10.0.0.2`
- `10.0.0.9`
- `10.0.0.10`

The scan also identified the MAC addresses associated with the discovered hosts. For example, `10.0.0.1` was associated with a QEMU virtual network interface, while `10.0.0.2` and `10.0.0.9` were associated with Oracle VirtualBox virtual network interfaces.

After completing the scan, I opened the **Topology** section in Zenmap, enabled the legend, and saved the network topology in PDF format. This provided a visual representation of the discovered devices and their relationships within the local network.

## 🚨 5. Risk Analysis / Impact

The findings below are based on the information collected during the footprinting and network scanning activities. They represent potential risks and observations, not confirmed vulnerabilities.

| # | Risk / Finding | Evidence / Observation | Potential Impact | Risk Level |
|---|---|---|---|---|
| 1 | Web technology information exposed | WhatWeb identified WordPress, WP Download Manager, Apache, and the server IP address. | Attackers may use exposed technology details to identify software that requires further security review. | Medium |
| 2 | Server IP address identifiable | Nslookup resolved `networkwalks.com` to `192.232.216.135`. | The IP address provides information about the location of the web service and may support further reconnaissance. | Low |
| 3 | HTTP technical information exposed | Curl returned HTTP headers and exposed the `/wp-json/` endpoint. | This information may assist technology fingerprinting and further enumeration of the web application. | Low |
| 4 | WAF technology identifiable | Wafw00f identified ModSecurity (SpiderLabs). | Revealing the WAF may provide attackers with information about the website’s security architecture. | Low |
| 5 | DNS infrastructure information exposed | DNSRecon identified DNS, mail, SPF, TXT, and service-related records. | DNS information can help an attacker build a broader profile of the organisation’s infrastructure. | Medium |
| 6 | Publicly exposed camera interfaces | GHDB identified publicly accessible security camera pages using Google dorks. | Exposed camera interfaces may allow unauthorised viewing or access if they are not properly secured. | High |
| 7 | Publicly available documents | GHDB identified downloadable mathematics PDF files using Google search operators. | Publicly indexed documents may expose sensitive information if they are not intended for public access. | Low |
| 8 | Email address exposed through OSINT | Maltego identified `info@networkwalks.com` associated with the target domain. | Public email addresses may be used for reconnaissance, phishing, or social-engineering attempts. | Medium |
| 9 | Limited OSINT results from theHarvester | theHarvester did not return results from some data sources because API keys were missing. | Incomplete OSINT results may limit the effectiveness of reconnaissance activities. | Low |
| 10 | Multiple live hosts visible on local network | Zenmap identified four live hosts on the local subnet. | Unknown or unauthorised devices may be present on the network and should be reviewed. | Medium |

**Risk level key:** 🔴 Critical, 🟠 High, 🟡 Medium, 🟢 Low.

The risks identified during these activities relate mainly to information exposure and network visibility. No exploitation, vulnerability validation, or unauthorised access was performed during the practical exercises.

## ✅ 6. Recommendations

1. **Review publicly exposed technology information.** Organisations should regularly review what information about their web technologies, CMS, plugins, and server configuration is publicly visible.

2. **Keep software updated.** WordPress, plugins, web servers, and other web technologies should be regularly updated and reviewed against current security advisories.

3. **Review HTTP response headers.** HTTP headers should be checked to ensure that unnecessary technical information is not exposed to the public.

4. **Review DNS records regularly.** DNS records should be checked periodically to ensure that only required information and services are publicly available.

5. **Properly configure and monitor the WAF.** ModSecurity should remain enabled, properly configured, and regularly monitored to help protect the web application.

6. **Secure internet-facing devices.** Security cameras, routers, and other internet-facing devices should use strong authentication, updated firmware, and restricted access where possible.

7. **Review publicly indexed content.** Organisations should regularly search for exposed files, directories, documents, and devices to ensure that sensitive information is not publicly accessible.

8. **Limit publicly available email addresses.** Organisations should review which email addresses are publicly displayed and consider using role-based addresses where appropriate.

9. **Perform regular internal network discovery.** Organisations should periodically scan their own networks to identify active devices and detect unknown or unauthorised systems.

10. **Investigate unknown devices.** Any unexpected device discovered during network scanning should be investigated and verified as authorised.

11. **Maintain network documentation.** Network topology, IP addressing, and device information should be documented and updated regularly.

12. **Perform security testing with authorisation.** Reconnaissance and scanning should only be performed against systems and networks where appropriate written authorisation has been provided.

## 🏁 7. Conclusion

During Week 2 of the Cybersecurity and Ethical Hacking internship, I completed five practical modules covering reconnaissance, footprinting, OSINT, and network scanning. These modules were **WK2-PM1 (Multiple Kali Tools), WK2-PM2 (GHDB), WK2-PM3 (Maltego), WK2-PM4 (theHarvester), and WK2-PM5 (Zenmap Scanning)**.

In the footprinting activities, I used multiple Kali Linux tools to collect information about the authorised target domain. I learned how WHOIS can provide domain registration information, WhatWeb can identify web technologies, Nslookup can resolve domain names, Curl can inspect HTTP headers, Wafw00f can identify a WAF, and DNSRecon can enumerate DNS records.

I also used GHDB to understand how Google dorks can reveal publicly accessible information, Maltego to map relationships between domain-related information, and theHarvester to collect OSINT data. These activities showed that publicly available information can provide valuable insight into an organisation’s online presence.

In the network scanning activity, I used Zenmap to identify my local network configuration, discover active hosts, collect IP and MAC address information, and generate a network topology. The scan identified four live hosts on the local subnet and demonstrated how network discovery can provide visibility into connected devices.

Overall, these exercises showed that reconnaissance and scanning are important parts of cybersecurity. Even before attempting to exploit a system, a security professional can learn a significant amount about an environment by carefully analysing publicly available information and network responses.

I also learned that technical findings should be documented clearly. A good cybersecurity report should explain what was performed, what was discovered, what the observation means, what risk it may create, and what can be done to reduce that risk.

Finally, I learned that reconnaissance and scanning must always be performed within an authorised scope. These activities were completed as part of the assigned educational cybersecurity lab, using only authorised targets and the tester’s own local network.

## 📎 8. Evidence Collected

### 🪪 WHOIS

```text
whois networkwalks.com
```

The WHOIS results identified the domain registrar as GoDaddy, the creation date as 6 November 2019, and the expiry date as 6 November 2027. The name servers identified were `NS6135.HOSTGATOR.COM` and `NS6136.HOSTGATOR.COM`.

<img width="1920" height="923" alt="11-screenshot-whois" src="https://github.com/user-attachments/assets/12ced864-f63c-4c8f-a995-7a5e387a0401" />

<img width="1920" height="923" alt="12-screenshot-whois" src="https://github.com/user-attachments/assets/82524d06-de62-4eb1-abd2-493a4c485eb5" />

<img width="1920" height="923" alt="13-screenshot-wois" src="https://github.com/user-attachments/assets/4badf229-5766-45df-8200-288dff548f95" />

<img width="1920" height="923" alt="14-screenshot-whois" src="https://github.com/user-attachments/assets/709e2256-714a-422e-a5be-794008dc36ab" />



### 🕵️ WhatWeb

```text
whatweb networkwalks.com
```

The results identified Apache, WordPress, WP Download Manager, jQuery, Bootstrap, and the IP address `192.232.216.135`.

<img width="1920" height="923" alt="10-screenshot-whatweb" src="https://github.com/user-attachments/assets/ef909fe5-1490-49dd-b20f-8498f82ac796" />


### 🌍 Nslookup

```text
nslookup networkwalks.com
```

The domain resolved to `192.232.216.135`.

<img width="1920" height="923" alt="09-screenshot-nslookup" src="https://github.com/user-attachments/assets/b7b16b9d-34db-48bd-bb1a-1f0fdcc5ee78" />


### 🔗 Curl

```text
curl -I https://networkwalks.com
```

The HTTP response identified Apache as the server and exposed the WordPress REST API endpoint `/wp-json/`.

<img width="1920" height="923" alt="08-screenshot-curl" src="https://github.com/user-attachments/assets/c37315c1-0a66-4a22-baf1-9e0298784262" />


### 🧱 Wafw00f

```text
wafw00f networkwalks.com
```

The scan identified ModSecurity (SpiderLabs) as the WAF protecting the website.

<img width="1920" height="923" alt="07-screenshot-wafw00f" src="https://github.com/user-attachments/assets/98f0e0b0-c426-4a12-b21f-0d0b4bdc1d29" />


### 🕸️ Maltego

Maltego identified `info@networkwalks.com` as an email address associated with `networkwalks.com`.

<img width="1721" height="906" alt="05-screenshot-maltego" src="https://github.com/user-attachments/assets/19311cea-5cc4-4d55-acfe-f4e9243ac209" />

<img width="1720" height="903" alt="06-screenshot-maltego" src="https://github.com/user-attachments/assets/99aca94b-f0e2-4527-9b02-6fb57e0302d3" />


### 🌐 theHarvester

```text
theHarvester -d microsoft.com -l 1000 -b baidu
theHarvester -d microsoft.com -l 50 -b all
```

The Baidu scan did not return results. The `all` scan showed that several data sources required API keys that were not configured.

<img width="1143" height="796" alt="01-screenshot-theharvest" src="https://github.com/user-attachments/assets/d2a7d3a2-7da5-41cb-8f07-ca2671729edc" />

<img width="1130" height="801" alt="02-screenshot-theharvest" src="https://github.com/user-attachments/assets/72f0716d-b8a5-4e99-b3e5-54d482936b8c" />


### 🖥️ Zenmap

```text
nmap -sn 10.0.0.0/24
```

The scan identified four live hosts: `10.0.0.1`, `10.0.0.2`, `10.0.0.9`, and `10.0.0.10`.

<img width="1046" height="865" alt="03-screenshot-nmap" src="https://github.com/user-attachments/assets/6eacf6f0-3cab-41fb-b975-18b064ce30f1" />

<img width="1027" height="863" alt="04-screenshot-nmap" src="https://github.com/user-attachments/assets/588c7b7f-d013-4707-a8e5-3d0260178aaf" />


## 👤 Author Information

**Author:** Landry Kasapato Semilwo  
**Role:** Junior Cybersecurity Engineer  
**Program:** Cybersecurity program at Networkwalks  
**Week:** 02  
**Repository:** GitHub 
**LinkedIn:** https://www.linkedin.com/in/landry-semilwo-756904258/
