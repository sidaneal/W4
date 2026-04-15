# W4
Step,Phase,Tool Used,Action Taken,Key Finding,Screenshot
1,Metadata Extraction,exiftool,Analyzed ocean.jpg attributes.,"Found ""THIS IS THE HIDDEN FLAG"" in the Comment field.",![Metadata Analysis](path/to/screenshot1.png)
2,String Analysis,strings,Extracted text from computer.jpg.,Identified hardware signatures (APPL) and library (lcms).,![String Analysis](path/to/screenshot2.png)
3,Steganography,binwalk,Probed dog.jpg for embedded data.,Discovered a hidden Zip archive at offset 0x1589D.,![Steganography](path/to/screenshot3.png)
4,Integrity Check,file,Verified true file types of rubiks.jpg and solitaire.exe.,Confirmed both were PNGs disguised as other formats.,![Integrity Check](path/to/screenshot4.png)
5,Domain Recon,whois,Queried unikl.edu.my.,Mapped organization ownership and Name Servers.,![Whois Result](path/to/screenshot5.png)
6,DNS Resolution,nslookup,Resolved the target domain to an IP.,Mapped the primary server IP for future assessment.,![DNS Lookup](path/to/screenshot6.png)
