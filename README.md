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

#Beyond metadata.
 I'm exploring Google Dorking via the GHDB and DorkGPT to understand how misconfigured servers leak sensitive data. Mastering reconnaissance is the first step in a successful forensic investigation.

I am learning to use the Google Hacking Database (GHDB) to identify misconfigured IoT devices and exposed web servers. This highlights the importance of proper credential management and network security to prevent unauthorized data exposure.
