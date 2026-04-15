# W4
# KB21403: Footprinting and Reconnaissance Lab

This repository documents my lab work for the **Footprinting and Reconnaissance module**. The objective was to identify potential information leakage, perform passive OSINT gathering, and analyze the integrity of various digital artifacts.

---

## Methodology: Passive Footprinting and Data Analysis

| Step | Phase                | Tool Used | Action Taken                                      | Key Finding                                              | Screenshot |
|------|---------------------|----------|--------------------------------------------------|----------------------------------------------------------|------------|
| 1    | Metadata Extraction | exiftool | Analyzed `ocean.jpg` attributes                  | Found **"THIS IS THE HIDDEN FLAG"** in Comment field      | ![Metadata Analysis](path/to/screenshot1.png) |
| 2    | String Analysis     | strings  | Extracted text from `computer.jpg`               | Identified hardware signatures (APPL) and library (lcms)  | ![String Analysis](path/to/screenshot2.png) |
| 3    | Steganography       | binwalk  | Probed `dog.jpg` for embedded data               | Found hidden ZIP archive at offset `0x1589D`              | ![Steganography](path/to/screenshot3.png) |
| 4    | Integrity Check     | file     | Verified actual file types                       | Found PNG files disguised as JPG/EXE                      | ![Integrity Check](path/to/screenshot4.png) |
| 5    | Domain Recon        | whois    | Queried `unikl.edu.my`                           | Identified ownership and name servers                     | ![Whois Result](path/to/screenshot5.png) |
| 6    | DNS Resolution      | nslookup | Resolved domain to IP address                    | Identified primary server IP                              | ![DNS Lookup](path/to/screenshot6.png) |

---

## Technical Execution Flow

### 1. Information Gathering (OSINT)

I performed **network footprinting** on the target organization using passive techniques.  
By using `whois` and `nslookup`, I successfully identified:

- Infrastructure ownership  
- Domain details  
- Primary server IP address  

This was done **without directly interacting with internal systems**, minimizing detection risk.

---

### 2. Artifact Analysis & Forensics

I conducted deep file analysis to uncover hidden or sensitive information.

#### Metadata & Strings
- Used `exiftool` and `strings`
- Revealed hidden data such as:
  - Comments
  - OS-related artifacts
  - Software/library signatures

#### Steganography
- Used `binwalk`
- Successfully detected and extracted a hidden archive
- Demonstrated how attackers conceal payloads inside media files

---

### 3. Detecting Deception

To verify file authenticity, I used the `file` command:

- Identified mismatched file extensions
- Discovered:
  - `.jpg` files that were actually PNG
  - `.exe` files that were not executable


---
