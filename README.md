# My-First-Project-My-Cyber-Journey.
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
