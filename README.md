# 🔐 PDF Password Auditing | John the Ripper CLI

**Cybersecurity Internship | Networkwalks | Week 03**

<div align="center">

![Kali Linux](https://img.shields.io/badge/Platform-Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![John the Ripper](https://img.shields.io/badge/Tool-John%20the%20Ripper-8B0000?style=for-the-badge)
![Module](https://img.shields.io/badge/Module-PDF%20Password%20Auditing-222222?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-2EA44F?style=for-the-badge)

*Extract · Audit · Recover · Verify*

</div>

---

## 📌 Table of Contents

- [1. Project Overview](#1-project-overview)
- [2. Lab Environment](#2-lab-environment)
- [3. Module 1 — John the Ripper CLI](#3-module-1--john-the-ripper-cli)
- [4. Module 2 — Networkwalks Security Tool](#4-module-2--networkwalks-security-tool)
- [5. Results and Flag Capture](#5-results-and-flag-capture)
- [6. Key Learnings](#6-key-learnings)
- [7. Security Recommendations](#7-security-recommendations)
- [8. Conclusion](#8-conclusion)
- [9. Disclaimer](#9-disclaimer)

---

## 1. Project Overview

This repository documents my **Week 03 cybersecurity practicals** focused on PDF password security and password recovery techniques as part of my cybersecurity internship at **Networkwalks**.

The objective of these exercises was to understand how password-protected PDF documents can be audited using password recovery tools and dictionary-based password testing.

During this week's practicals, I completed two modules:

### Module 1 — John the Ripper CLI

Used the command-line version of **John the Ripper** to perform password auditing against a password-protected PDF.

The practical involved extracting the PDF's password hash, processing it using John the Ripper, recovering the password through dictionary-based testing, and successfully capturing the assigned flag.

### Module 2 — Networkwalks Security Tool

Used the Networkwalks Security Tool to perform password recovery on a separate password-protected PDF and completed the assigned practical.

### Objectives

- Understand the fundamentals of PDF password protection.
- Learn how password-related hash information is extracted from encrypted PDF documents.
- Explore the command-line interface of John the Ripper.
- Understand dictionary-based password auditing.
- Recover a password from an authorized training PDF.
- Verify successful password recovery.
- Complete the assigned practicals and capture the flags.

---

## 2. Lab Environment

| Parameter | Details |
|:--|:--|
| Trainee | Ayesha Kazi |
| Internship Organization | Networkwalks |
| Internship Week | Week 03 |
| Operating System | Kali Linux |
| Domain | Cybersecurity & Ethical Hacking |
| Primary Tool | John the Ripper CLI |
| Password Auditing Technique | Dictionary Attack |
| Target File Type | Password-protected PDF |
| Secondary Tool | Networkwalks Security Tool |
| Verification | PDF Viewer |

---

## 3. Module 1 — John the Ripper CLI

### 3.1 Tool Overview

**John the Ripper**

John the Ripper is an open-source password security auditing tool used to test password strength and recover passwords from supported hash formats.

The command-line interface provides direct access to its password auditing capabilities, allowing users to specify hash files, wordlists, and other options through terminal commands.

For this practical, John the Ripper was used to audit the password hash extracted from an encrypted PDF training document.

### 3.2 PDF Hash Extraction

Password-protected PDF documents contain encryption-related information used during password verification.

A compatible PDF hash extraction utility can convert this information into a representation that password auditing tools can process.

The extracted hash is not the original password. It provides the information required to test password candidates against the document's password verification mechanism.

### 3.3 Practical Workflow

#### Step 1 — Identify the encrypted PDF

Selected the assigned password-protected PDF training document for the practical.

**Target file:** `My Locked PDF.pdf`

> Replace this filename if your actual training document had a different name.

#### Step 2 — Extract the PDF hash

Used a compatible PDF hash extraction utility to obtain the password-related hash information from the encrypted document.

The extracted hash was saved in a file for use with John the Ripper.

Example output filename:

`pdf_hash.txt`

#### Step 3 — Prepare the hash for auditing

The extracted hash was prepared in a format compatible with John the Ripper's PDF password auditing support.

The hash file served as the input for the password recovery process.

#### Step 4 — Perform dictionary-based password auditing

Used the command-line version of John the Ripper to test candidate passwords against the extracted PDF hash.

The dictionary-based approach checks password candidates from a wordlist rather than attempting every possible password combination.

Example command structure:

```bash
john --wordlist=<WORDLIST_PATH> pdf_hash.txt
```

The actual wordlist path and command options may vary depending on the lab environment.

#### Step 5 — Recover the password

John the Ripper successfully identified a matching password candidate for the encrypted PDF.

The recovered password was then used to verify access to the protected document.

#### Step 6 — Verify the recovered password

Opened the original PDF in a PDF viewer and entered the recovered password.

The document was successfully unlocked, confirming that the recovered password was valid.

#### Step 7 — Capture the flag

After completing the password recovery practical, successfully captured the assigned flag from the training platform.

**Module 1 Result:** Password recovery and flag capture completed successfully.

### 3.4 Module 1 Observation

This practical demonstrated how a command-line password auditing tool can be used to evaluate the strength of a password-protected PDF.

It also helped me understand the relationship between hash extraction, password candidate testing, password recovery, and verification against the original document.

---

## 4. Module 2 — Networkwalks Security Tool

### 4.1 Tool Overview

The second module involved using the **Networkwalks Security Tool** to perform password recovery on another password-protected PDF.

The practical provided an opportunity to explore an alternative password auditing workflow and compare it conceptually with the command-line approach used in Module 1.

### 4.2 Practical Implementation

#### Step 1 — Select the protected PDF

Selected the assigned encrypted PDF training document for the second module.

**Target file:** `My Locked PDF 2.pdf`

#### Step 2 — Submit the document for password recovery

Used the Networkwalks Security Tool to process the assigned PDF and perform the password recovery exercise.

#### Step 3 — Complete the password recovery task

The tool successfully identified the password for the protected training document.

#### Step 4 — Verify the result

Used the recovered password to access the protected PDF and confirmed successful completion of the practical.

#### Step 5 — Capture the flag

Successfully captured the assigned flag after completing the second module.

### 4.3 Module 2 Observation

This module demonstrated another approach to PDF password recovery and reinforced the importance of understanding how password auditing tools evaluate candidate passwords.

It also provided an opportunity to compare a command-line auditing workflow with a dedicated security tool.

---

## 5. Results and Flag Capture

Both practical modules were completed successfully.

| Module | Tool Used | Result |
|:--|:--|:--|
| Module 1 | John the Ripper CLI | PDF password recovered |
| Module 1 | John the Ripper CLI | Flag captured |
| Module 2 | Networkwalks Security Tool | PDF password recovered |
| Module 2 | Networkwalks Security Tool | Flag captured |

### Completion Summary

- Successfully recovered the password of a protected PDF using John the Ripper CLI.
- Verified the recovered password by opening the original document.
- Successfully captured the flag for Module 1.
- Completed the second PDF password recovery practical using the Networkwalks Security Tool.
- Successfully captured the flag for Module 2.

### Screenshots

Add your actual screenshots to a folder named `screenshots/` in the repository.

| Screenshot | Description |
|:--|:--|
| `01-pdf-hash-extraction.png` | Extracted PDF hash |
| `02-john-cli-command.png` | John the Ripper CLI command |
| `03-john-password-recovered.png` | Password recovery result |
| `04-module1-flag.png` | Module 1 flag capture |
| `05-networkwalks-tool.png` | Networkwalks Security Tool |
| `06-module2-result.png` | Module 2 password recovery result |
| `07-module2-flag.png` | Module 2 flag capture |
| `08-pdf-verification.png` | Successfully unlocked PDF |

### Screenshot Gallery

**PDF Hash Extraction**

![PDF Hash Extraction](screenshots/01-pdf-hash-extraction.png)

**John the Ripper CLI**

![John the Ripper CLI](screenshots/02-john-cli-command.png)

**Password Recovery Result**

![John the Ripper Result](screenshots/03-john-password-recovered.png)

**Module 1 Flag Capture**

![Module 1 Flag](screenshots/04-module1-flag.png)

**Networkwalks Security Tool**

![Networkwalks Security Tool](screenshots/05-networkwalks-tool.png)

**Module 2 Result**

![Module 2 Result](screenshots/06-module2-result.png)

**Module 2 Flag Capture**

![Module 2 Flag](screenshots/07-module2-flag.png)

**PDF Password Verification**

![PDF Verification](screenshots/08-pdf-verification.png)

> The screenshot paths will display correctly after the corresponding images are uploaded to the repository. Use screenshots from your own practicals.

---

## 6. Key Learnings

### 1. PDF Password Security

Developed a better understanding of how password-protected PDF documents use encryption and password verification to restrict access.

### 2. Hash Extraction

Learned how password-related information can be extracted from encrypted PDF documents and prepared for auditing.

### 3. John the Ripper CLI

Gained practical exposure to using John the Ripper through the terminal to perform password auditing.

### 4. Dictionary-Based Password Attacks

Understood how password candidates from a wordlist are tested against extracted hash information.

### 5. Password Recovery and Verification

Learned the importance of verifying a recovered password against the original document rather than relying only on a tool's success notification.

### 6. Tool Comparison

Explored two different approaches to PDF password recovery:

- Command-line password auditing using John the Ripper.
- Password recovery using the Networkwalks Security Tool.

### 7. Password Strength

Observed how predictable and commonly used passwords can make encrypted documents more vulnerable to dictionary-based password auditing.

---

## 7. Security Recommendations

Based on the practical exercises, the following practices can help improve PDF password security:

- Use long, unique, and unpredictable passwords.
- Avoid common words, personal information, and predictable patterns.
- Do not reuse passwords across multiple documents.
- Use appropriate PDF encryption settings.
- Store document passwords securely.
- Review the security of sensitive documents periodically.
- Perform password auditing only on files for which you have permission.

A strong encryption mechanism is important, but password selection also plays a significant role in the overall security of a protected document.

---

## 8. Conclusion

The Week 03 practicals provided hands-on experience with **PDF password auditing and recovery techniques**.

Through John the Ripper CLI, I successfully recovered the password of a protected PDF, verified access to the document, and captured the assigned flag.

The second module using the Networkwalks Security Tool further strengthened my understanding of password recovery workflows and the importance of verifying successful results.

Overall, this week's exercises helped me connect theoretical concepts such as encryption, hash extraction, password verification, and dictionary-based attacks with practical cybersecurity tools.

The most important takeaway was that password security depends not only on encryption but also on the strength and unpredictability of the password protecting the document.

---

## 9. Disclaimer

This repository is maintained for educational and documentation purposes as part of the Networkwalks Cybersecurity Internship.

All practical activities were conducted using assigned training documents in an authorized learning environment.

The techniques documented here are intended for legitimate password security auditing and educational use. They must not be used to access or recover passwords from documents without the owner's permission or appropriate authorization.

---

## 👩‍💻 Author

**Ayesha Kazi**

Cybersecurity Intern | Networkwalks

**Program:** Cybersecurity Internship  
**Week:** 03  
**Domain:** Cybersecurity & Ethical Hacking  
**Practical Topic:** PDF Password Auditing using John the Ripper CLI

---

<div align="center">

**🔐 Learn · Practice · Audit · Secure**

*Building a stronger cybersecurity foundation, one practical at a time.*

</div>
