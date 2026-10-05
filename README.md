EFTA Redaction Comparison

While manually scraping the Department of Justice Epstein Files library, I found the same email released twice under two different Bates numbers, EFTA00952117 and EFTA02230480. The two releases were redacted differently. One hides the student's name and shows the sender. The other hides the sender and shows the student's name. Read together, they show Lesley Groff reporting to Jeffrey Epstein on her efforts to get an I-20 issued through the American Language Communication Center (ALCC) for a Russian student named Anna.

This repository contains the full forensic report documenting how I preserved, verified, and examined both files.

What I did

I hashed both PDFs in FTK Imager and HashCalc before doing anything else, then staged them on a separate FAT32 volume and imaged that volume with FTK Imager. I verified the image and examined it in EnCase and Autopsy, and confirmed that every tool produced matching MD5 and SHA1 values for both files. I ran keyword searches in Autopsy for the names and Bates numbers, checked document metadata in Autopsy and FOCA, documented the case and chain of custody in OSForensics, and examined the internal structure of each PDF in the OSForensics hex viewer.

Findings

Both files kept identical hashes across every tool, so the evidence did not change at any point in the examination. Each redaction is burned into the page image, and the text layer was added afterward, so neither file leaks redacted text by itself. The names are exposed only because the two releases were redacted differently. The hex view shows that each PDF was built in three stages: the scanned page, an OCR text layer, and the Bates stamp. The two versions have different page sizes, image dimensions, and color settings, and EFTA02230480 carries an earlier R1 Bates number, EFTA_R1_00982796. That shows the email went through more than one production and the redactions were never reconciled.

Tools

FTK Imager 4.7.2.11, HashCalc, EnCase Forensic 8.09, Autopsy 4.21.0, FOCA, and OSForensics, run in the UMGC DFCS 615 virtual lab.

Author

Aliya Feuer-Whittlesey

The redactions themselves were done right. They're burned into the page images, and no text sits under the boxes. What exposed the names was the inconsistency between two releases of the same email.
