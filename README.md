
## My-First-Project-My-Cyber-Journey.
This is the place where I saved what I learned in my course.

## Lab Notes_ Day-1
Today I learned how I open GitHub account, and how I create repository.

## During My Favorite Course (OSINT) Open Source Intelligence.
 In our past lecture about Metadata, something about it is we enjoyed and learned a lot, for tracking social media accounts and track real picture Data isn't easy but we'll happy.

# Image Geolocation & Forensic Metadata Analysis

## Project Objective
This project demonstrates the extraction of high-precision GPS metadata from a digital image using command-line forensic tools in Kali Linux.

## Forensic Evidence Extracted
- **File Name:** fdf.jpg
- **Latitude:** 16.977852 N
- **Longitude:** 7.981417 E
- **Timestamp:** 2026:02:11 00:34:28
- **Altitude:** 518m Above Sea Level

## Methodology
Using **ExifTool**, I bypassed standard file properties to retrieve 6-decimal precision coordinates, allowing for exact mapping of the image capture location in Agadez, Niger.

### Command Execution:
`exiftool -c "%.6f" -gpslatitude -gpslongitude fdf.jpg

# Beyond metadata.
 I'm exploring Google Dorking via the GHDB and DorkGPT to understand how misconfigured servers leak sensitive data. Mastering reconnaissance is the first step in a successful forensic investigation.

I am learning to use the Google Hacking Database (GHDB) to identify misconfigured IoT devices and exposed web servers. This highlights the importance of proper credential management and network security to prevent unauthorized data exposure.

## Reconnaissance & OSINT Skills.
- **Google Dorking**: Familiar with using advanced search operators (Dorks) via the Google Hacking Database (GHDB).
- **Automation Tools**: Experienced in using **DorkGPT** to generate precise queries for identifying misconfigured servers and exposed IoT devices.
- **Ethical Analysis**: Understanding the security risks of exposed webcams and databases to help organizations improve their network security.
## Future Research Goals
- Master **Shodan** for global device reconnaissance.
- Understand **Common Vulnerabilities and Exposures (CVEs)** associated with IoT devices.
- Develop professional reporting skills for **Vulnerability Assessment**.

# Advanced Reconnaissance: Shodan Filters.

In my research, I have explored the use of Shodan filters to identify misconfigured assets globally and locally.
has_screenshot:true: To visualize exposed interfaces.
country:"NG" port:80: To identify open web servers within Nigeria.
"authentication disabled": To audit devices with critical security bypasses.

Note: All activities are conducted for educational and defensive research purposes only.


## Research Methodology & OSINT Insights
- **Multi-Engine Search**: Utilizing Bing for IP-based reconnaissance and Google for advanced syntax dorking.
- **Geospatial Forensics**: Leveraging Google Earth Pro's historical imagery to perform temporal-spatial analysis on extracted coordinates.
- **Asset Discovery**: Understanding the limitations of free-tier Shodan vs. professional API access for large-scale vulnerability scanning.

- **Google Earth Pro**: Utilized for precise location verification and street-level visualization of forensic coordinates.

## Advanced OSINT Techniques
- **Geospatial Verification**: Using Google Earth Pro to map extracted coordinates (16.977852, 7.981417) to a physical terrain in Agadez, Niger.
- **Reverse Image Search**: Conducted verification using Yandex and Google Lens to ensure image authenticity and trace its digital origin.

## Specialized OSINT Resources
- **Frameworks**: Following the IntelTechniques methodology (Michael Bazzell) for advanced people-search and digital footprints.
- **Privacy Hardening**: Implementing privacy techniques to secure personal data while conducting investigative research.
## Hybrid Cybersecurity Skills (Purple Teaming)
- **Offensive (Red Team)**: Performing reconnaissance using Google Dorks, Shodan, and Sherlock to identify attack vectors.
- **Defensive (Blue Team)**: Analyzing image metadata (EXIF) and network logs to investigate security incidents and track origins.
- **Network Architecture**: Understanding the distinction between Public and Private IP addressing and the role of NAT (Network Address Translation) in home/enterprise networks.
- **Network Discovery**: Identifying the role of RFC 1918 private address spaces (e.g., 10.0.0.0/8) and understanding NAT (Network Address Translation) for public internet access.
- **Network Interfaces**: Understanding the role of multiple interfaces (eth0, wlan0, tun0) during VPN-based penetration testing.
- **NAT Security**: Evaluating how Private IP structures (10.0.0.0/8) provide a basic layer of security against unsolicited inbound traffic.
- **ISP Identification**: Understanding how IP Geolocation reveals ISP data (e.g., SpaceX/Starlink) and its significance in digital investigations.
- **Address Resolution**: Differentiating between local gateway IPs (192.168.x.x) and external-facing public IPs provided by ISPs.
## External Perimeter Auditing
- **Public IP Analysis**: Identifying Starlink's IP range (e.g., 129.222.x.x) and performing external port auditing to assess network vulnerability.
- **Firewall Testing**: Using tools like Nmap and online scanners to verify inbound traffic filtering on personal network gateways.

- # Network Traffic Analysis: Voucher-Based Wi-Fi Network

## Project Overview
This analysis focused on investigating the traffic flow, protocol distribution, and security posture of a local, open Wi-Fi network running a captive portal (voucher system). The goal was to understand how client devices interact with the gateway and identify potential vectors for MAC spoofing or session hijacking.

## Technical Methodology & Findings

1. **Capture Environment & Transfer**
   - Captured raw network traffic on-site.
   - Saved the output as a `.pcapng` file and moved it into a Kali Linux environment for deep packet inspection using Wireshark.

2. **Endpoint & OUI Resolution**
   - Enabled MAC/Network Name Resolution within Wireshark's **Conversations** and **Endpoints** tabs to map Layer 2 and Layer 3 addresses to hardware vendors.
   - Successfully identified the network gateway as a MikroTik device via the **Routerboard** OUI.
   - Identified various connected client devices, including local workstations (**Pcsystem**) and mobile endpoints (e.g., **Infinix** devices).

3. **Protocol Breakdown: UDP & DNS Dominance**
   - Filtered traffic to find that **UDP** was the dominant transport layer protocol.
   - A large portion of UDP traffic was tied to **DNS (Port 53)** queries as client devices resolved external domains for applications like TikTok and Instagram.
   - The remaining bulk traffic utilized the **QUIC** protocol over UDP, indicating heavy video streaming across the network.

4. **Payload Inspection & Encryption Realities**
   - Analyzed packet payloads via Hex Dump and ASCII views.
   - Validated that while metadata (DNS queries, MAC vendor IDs, and frame headers) is fully visible in plaintext on an open network, the actual application layer payloads remain heavily encrypted via modern TLS/QUIC standards, showing as randomized ciphertext.

## Cybersecurity Takeaways
Operating an unencrypted, open captive portal leaves the network vulnerable to passive DNS sniffing and rogue active attacks like MAC spoofing (where an unauthorized user clones an authenticated client's hardware address to bypass voucher limits). Monitoring the packet stream using Wireshark provides the necessary visibility to detect duplicate IP assignments and anomalous traffic spikes.

Lab Notes: MikroTik Captive Portal & Network Security Analysis
Objective
To analyze the security posture of an open, voucher-based MikroTik Wi-Fi network using traffic analysis and port scanning tools.

#Key Findings
MAC-to-IP Binding: The router maps active sessions to the client's default MAC address. Changing to a randomized MAC address bypasses the session and triggers the captive portal again. Returning to the default MAC successfully restores the internet session without needing a new voucher (a potential vector for MAC spoofing).

Hardened Firewall (Device Security):

External scans via Shodan yielded zero results (active firewall/CGNAT protection).

Local port scanning showed that administrative ports (like 8291 for Winbox, 80/443 for WebFig) are strictly filtered or closed to local users. The router itself is highly secured.

Unencrypted Over-the-Air Traffic: While the router's configuration is locked down, the open nature of the Wi-Fi means client DNS queries and network traffic are transmitted unencrypted over the air, leaving users vulnerable to sniffing and Man-in-the-Middle (MITM) attacks.

#Tools Used
Wireshark (Packet analysis)

Shodan (External OSINT reconnaissance)

Advanced IP Scanner (Local port scanning)

### 🏆 Certifications & Badges

*   **Introduction to Critical Infrastructure Protection (ICIP)** - *OPSWAT Academy* (July 2026)
    *   **Credential ID:** `x7Q_UkS4sg`
    *   **Topics Covered:** Securing critical infrastructure, OT/IT security, and defensive security frameworks.
    *   [Verify Credential](https://learn.opswatacademy.com/certificate/x7Q_UkS4sg)
