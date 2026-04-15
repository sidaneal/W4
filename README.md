# W4
# KB21403: Footprinting and Reconnaissance Lab

This repository documents my lab work for the **Footprinting and Reconnaissance module**. The objective was to identify potential information leakage, perform passive OSINT gathering, and analyze the integrity of various digital artifacts.

---

## Methodology: Passive Footprinting and Data Analysis

| Step | Phase                | Tool Used | Action Taken                                      | Key Finding                                              | Screenshot |
|------|---------------------|----------|--------------------------------------------------|----------------------------------------------------------|------------|
| 1    | Metadata Extraction | exiftool | Analyzed `ocean.jpg` attributes                  | Found **"THIS IS THE HIDDEN FLAG"** in Comment field      |<img width="936" height="564" alt="Screenshot 2026-04-15 155757" src="https://github.com/user-attachments/assets/4b532c8e-3196-4ec3-8d9e-cc38da691568" />|
| 2    | String Analysis     | strings  | Extracted text from `computer.jpg`               | Identified hardware signatures (APPL) and library (lcms)  | <img width="1003" height="639" alt="image" src="https://github.com/user-attachments/assets/8a06ba1c-6b00-4a07-94b7-07e44ac7e0bc" />|
| 3    | Steganography       | binwalk  | Probed `dog.jpg` for embedded data               | Found hidden ZIP archive at offset `0x1589D`              | <img width="650" height="650" alt="image" src="https://github.com/user-attachments/assets/476accc1-7792-40b2-9d98-06f651228bf1" /> <img width="642" height="198" alt="image" src="https://github.com/user-attachments/assets/2d13a741-0098-4cf7-a6bb-1282333c36df" />|
| 4    | Integrity Check     | file     | Verified actual file types                       | Found PNG files disguised as JPG/EXE                      | <img width="649" height="134" alt="image" src="https://github.com/user-attachments/assets/418fcb18-1f5d-4b8e-9f7c-52613106efd5" /><img width="656" height="74" alt="image" src="https://github.com/user-attachments/assets/600229da-4f65-4e00-99cd-0c6c2c3612f5" />|
| 5    | Domain Recon        | whois    | Queried `unikl.edu.my`                           | Identified ownership and name servers                     | <img width="657" height="505" alt="image" src="https://github.com/user-attachments/assets/3e2e273f-5e21-4294-bebc-4c5d26a15b4f" />|
| 6    | DNS Resolution      | nslookup | Resolved domain to IP address                    | Identified primary server IP                              | <img width="652" height="217" alt="image" src="https://github.com/user-attachments/assets/431b5e65-f92a-42f5-9a6f-8d9bf909abaa" />|

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
