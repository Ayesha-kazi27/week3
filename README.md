# 🔐 PDF Password Security | John the Ripper CLI

<p align="center">

**Networkwalks Cybersecurity Internship · Week 03**

*PDF Hash Extraction · Dictionary Attack · Password Recovery*

</p>

---

## 📌 Overview

This repository documents my Week 03 practical work on **PDF password security and dictionary-based password auditing** as part of the Networkwalks Cybersecurity Internship.

The exercise focused on understanding how password-protected PDF documents store password-verification information, how that information can be extracted into a compatible hash format, and how password auditing tools test candidate passwords against the extracted hash.

The practical involved two modules:

| Module | Practical |
|---|---|
| **Module 01** | PDF password auditing using John the Ripper CLI |
| **Module 02** | PDF hash extraction and dictionary comparison using Networkwalks tools |

The primary focus of this repository is the command-line workflow using **John the Ripper**, from hash extraction to password recovery and final verification.

> **Key takeaway:** PDF password auditing involves three distinct stages—hash extraction, password candidate testing, and verification against the original document.

---

## 🎯 Objectives

- Understand the fundamentals of password-protected PDF documents.
- Learn how PDF password hashes are extracted.
- Identify the relationship between a PDF hash and the original password.
- Use John the Ripper through the command-line interface.
- Perform a dictionary-based password audit on an authorized training PDF.
- Understand how wordlists are used during password auditing.
- Verify the recovered password against the original PDF.
- Capture the practical completion flag.
- Recognize the importance of strong and unpredictable passwords.

---

## 🧪 Lab Environment

| Parameter | Details |
|---|---|
| Trainee | Ayesha Kazi |
| Organization | Networkwalks |
| Internship | Cybersecurity Internship |
| Week | Week 03 |
| Domain | Cybersecurity & Ethical Hacking |
| Operating System | Kali Linux |
| Primary Tool | John the Ripper CLI |
| Edition | Jumbo, if applicable |
| Hash Extraction | PDF hash extraction utility |
| Attack Method | Dictionary-based password auditing |
| Target | Password-protected PDF |
| Verification | PDF viewer |

---

## 🛠️ Tools Used

### John the Ripper

John the Ripper is an open-source password security auditing tool that supports multiple hash formats and password-testing techniques.

In this practical, I used its command-line interface to load an extracted PDF hash and test password candidates from a wordlist.

### PDF Hash Extraction Utility

A PDF hash extraction utility converts the password-related information stored in an encrypted PDF into a format that can be processed by compatible password auditing tools.

The extracted hash is not the plaintext password. It is the input used during the password-auditing process.

### Wordlist

A wordlist contains candidate passwords that an auditing tool can test.

For this exercise, a dictionary-based approach was used to test candidate values against the extracted PDF hash.

### PDF Viewer

A PDF viewer was used to verify whether the recovered password successfully opened the original protected document.

---

# 1. Module 01 — John the Ripper CLI

## 1.1 Practical Workflow

The command-line workflow followed these stages:

```text
Password-Protected PDF
          │
          ▼
   PDF Hash Extraction
          │
          ▼
    Extracted PDF Hash
          │
          ▼
   John the Ripper CLI
          │
          ▼
   Dictionary-Based Attack
          │
          ▼
   Password Recovery
          │
          ▼
  PDF Password Verification
          │
          ▼
    Flag Capture
```

---

## 1.2 Step 1 — Identify the John the Ripper Installation

First, I checked whether John the Ripper was available in the Kali Linux environment.

```bash
john --version
```

To view the available command-line options:

```bash
john --help
```

This confirmed the tool's availability and provided an overview of the supported command-line operations.

**Screenshot:** `01-john-version.png`

---

## 1.3 Step 2 — Locate the PDF Hash Extraction Utility

Before running John the Ripper, the password-related hash information must be extracted from the protected PDF.

A compatible extraction utility, such as `pdf2john`, is commonly included with or distributed alongside John the Ripper Jumbo.

The exact script name and location may vary depending on the installation.

I located the PDF hash extraction utility available in my environment and used it to process the authorized training document.

**Screenshot:** `02-pdf-hash-extraction-tool.png`

---

## 1.4 Step 3 — Extract the PDF Hash

The protected PDF was processed using the PDF hash extraction utility.

Example command:

```bash
pdf2john.pl "My Locked PDF1.pdf" > pdf_hash.txt
```

Depending on the installed version, the utility may instead be available as `pdf2john.py` or under another compatible script name.

The output was saved to:

```text
pdf_hash.txt
```

The extracted hash uses a PDF-specific representation, commonly beginning with:

```text
$pdf$
```

This output contains the information required by compatible password auditing tools to test password candidates.

**Important:** The extracted hash is not the original password. It is a representation used during password verification.

**Screenshot:** `03-extracted-pdf-hash.png`

---

## 1.5 Step 4 — Prepare the Wordlist

A dictionary attack uses a wordlist containing possible password candidates.

In Kali Linux, a commonly used wordlist is:

```text
/usr/share/wordlists/rockyou.txt
```

If the wordlist is compressed, it can be decompressed using:

```bash
sudo gzip -dk /usr/share/wordlists/rockyou.txt.gz
```

The `-k` option preserves the original compressed file.

Before starting the attack, I confirmed that the wordlist was available at the expected path.

**Screenshot:** `04-wordlist-preparation.png`

---

## 1.6 Step 5 — Run the Dictionary Attack

With the extracted PDF hash and wordlist prepared, I used John the Ripper CLI to begin the password audit.

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt pdf_hash.txt
```

John the Ripper processed the extracted hash and tested candidate passwords from the specified wordlist.

The command-line interface displayed the progress and result of the password-auditing process.

**Screenshot:** `05-john-cli-dictionary-attack.png`

---

## 1.7 Step 6 — Display the Recovered Password

After the attack completed, I used the `--show` option to display the recovered result.

```bash
john --show pdf_hash.txt
```

This command displays passwords that John the Ripper has successfully recovered for the hashes stored in the specified file.

The recovered password was then used for the next stage of the practical.

**Screenshot:** `06-john-cli-password-recovered.png`

---

## 1.8 Step 7 — Verify the Password

To confirm the result, I opened the original password-protected PDF in a PDF viewer.

I entered the recovered password into the document's password prompt.

Successful access confirmed that the recovered password was valid for the training document.

This verification step was important because it confirmed the practical outcome against the original file rather than relying only on the command-line output.

**Screenshot:** `07-pdf-password-verification.png`

---

## 1.9 Step 8 — Capture the Completion Flag

After successfully completing the John the Ripper CLI exercise, I captured the completion flag displayed by the Networkwalks training platform.

```text
[Insert your actual Module 1 flag here]
```

**Screenshot:** `08-jtr-cli-flag.png`

---

## 1.10 Module 01 — Results

| Stage | Result |
|---|---|
| PDF hash extraction | Completed |
| Hash file preparation | Completed |
| Wordlist configuration | Completed |
| John the Ripper CLI execution | Completed |
| Password recovery | Successful |
| PDF password verification | Successful |
| Flag capture | Completed |

### Observation

This module provided hands-on experience with the command-line workflow of John the Ripper. It demonstrated how an extracted PDF hash can be processed using a wordlist and how the recovered password can be verified against the original document.

It also reinforced the importance of using a compatible hash format and correctly specifying the input hash file and wordlist.

---

# 2. Module 02 — Networkwalks PDF Hash Analysis Tools

## 2.1 Tools Used

### Networkwalks Hash Calculator

The Hash Calculator was used to extract password-related hash information from an encrypted PDF document.

### Networkwalks Comparison Tool

The Comparison Tool was used to test password candidates against the extracted PDF hash using a dictionary-based comparison process.

### PDF Viewer

A PDF viewer was used to verify the recovered password by opening the corresponding protected document.

---

## 2.2 Practical Workflow

```text
Password-Protected PDF
          │
          ▼
Networkwalks Hash Calculator
          │
          ▼
   Extracted PDF Hash
          │
          ▼
Networkwalks Comparison Tool
          │
          ▼
 Dictionary-Based Comparison
          │
          ▼
   Successful Password Match
          │
          ▼
    PDF Password Verification
          │
          ▼
    Module 2 Flag Capture
```

---

## 2.3 Step 1 — Extract the PDF Hash

I accessed the Networkwalks Hash Calculator and selected the PDF hash extraction option.

The authorized training PDF was submitted to the tool, which processed the encrypted document and generated a PDF-compatible hash representation.

The extracted hash was then used as input for the password comparison stage.

**Screenshot:** `09-networkwalks-hash-calculator.png`

---

## 2.4 Step 2 — Submit the Hash for Comparison

After extracting the hash, I opened the Networkwalks Comparison Tool.

I entered the extracted PDF hash into the appropriate input field and initiated the dictionary-based comparison process.

The tool tested candidate passwords against the supplied hash and displayed the progress of the operation.

**Screenshot:** `10-networkwalks-comparison-tool.png`

---

## 2.5 Step 3 — Observe the Password Match

The comparison process identified a matching password candidate and displayed a successful completion notification.

This indicated that a candidate from the tested dictionary matched the password-verification information extracted from the PDF.

**Screenshot:** `11-networkwalks-password-match.png`

---

## 2.6 Step 4 — Verify the Recovered Password

I used the recovered password to open the corresponding protected PDF.

The document accepted the password and opened successfully, confirming the result of the comparison process.

**Screenshot:** `12-networkwalks-pdf-verification.png`

---

## 2.7 Step 5 — Capture the Module 2 Flag

After completing the second practical, I captured the completion flag displayed by the Networkwalks training platform.

```text
[Insert your actual Module 2 flag here]
```

**Screenshot:** `13-networkwalks-flag.png`

---

# 3. Results and Flag Capture

The Week 03 practical involved two separate password-auditing exercises.

| Module | Tool | Outcome |
|---|---|---|
| Module 01 | John the Ripper CLI | PDF password successfully recovered |
| Module 02 | Networkwalks Hash Calculator + Comparison Tool | Password match successfully identified |

### Completion Flags

| Module | Flag |
|---|---|
| Module 01 | `[Insert actual flag]` |
| Module 02 | `[Insert actual flag]` |

Both modules provided practical exposure to password auditing and the process of verifying recovered passwords against protected PDF documents.

---

# 4. Understanding the Password Auditing Process

One of the most important concepts learned during this exercise was the distinction between hash extraction, password auditing, and password verification.

### Hash Extraction

The extraction utility processes the encrypted PDF and generates a representation of its password-verification information.

### Password Auditing

John the Ripper or another compatible auditing tool tests password candidates against the extracted hash.

### Password Recovery

When a candidate successfully matches the hash, the auditing tool identifies it as a recovered password.

### Password Verification

The recovered password is entered into the original PDF's password prompt to confirm that it successfully unlocks the document.

These stages form the complete workflow of a PDF password security assessment.

---

# 5. Key Observations

The following observations were made during the practical:

1. John the Ripper can be operated directly through the command-line interface without requiring a graphical front-end.
2. PDF password auditing requires a compatible hash representation extracted from the protected document.
3. The extracted PDF hash is not the plaintext password.
4. Dictionary attacks test predefined password candidates rather than generating every possible password combination.
5. The wordlist and hash file must be correctly specified when running John the Ripper.
6. The `--show` option can be used to display recovered passwords for the supplied hash file.
7. A successful password match should be verified against the original protected PDF.
8. Predictable passwords are more susceptible to dictionary-based password auditing.
9. Hash extraction, password recovery, and document verification are separate stages of the overall process.

---

# 6. Key Learnings

### 1. PDF Password Security

Learned how password-protected PDF documents use encryption and password-verification information to protect their contents.

### 2. Hash Extraction

Understood how password-related information can be extracted from an encrypted PDF and converted into a format supported by auditing tools.

### 3. John the Ripper CLI

Gained practical experience using John the Ripper through terminal commands to process an extracted hash and perform password auditing.

### 4. Dictionary-Based Attacks

Learned how wordlists are used to test candidate passwords against a password hash.

### 5. Command-Line Workflow

Developed a better understanding of specifying input files, wordlists, and command-line options during a password security assessment.

### 6. Password Verification

Learned why recovered passwords should be tested against the original document to confirm the result.

### 7. Tool Integration

Explored how different tools can be combined to perform hash extraction, password auditing, and verification.

### 8. Responsible Security Testing

Reinforced the importance of conducting password audits only on personal documents, authorized training files, or documents for which explicit permission has been granted.

---

# 7. Security Recommendations

Based on the observations from this exercise, the following practices can improve PDF password security:

- Use long, unique, and unpredictable passwords.
- Avoid common words, predictable patterns, and personal information.
- Avoid reusing passwords across documents and accounts.
- Use appropriate PDF encryption settings and security-supported software.
- Store document passwords securely.
- Avoid sharing passwords through unprotected communication channels.
- Perform password security assessments only with proper authorization.

A strong encryption mechanism is important, but password selection also plays a significant role in the overall security of a protected document.

---

# 8. Repository Structure

The repository can be organized as follows:

```text
Week-03-PDF-Password-Security/
│
├── README.md
│
├── screenshots/
│   ├── 01-john-version.png
│   ├── 02-pdf-hash-extraction-tool.png
│   ├── 03-extracted-pdf-hash.png
│   ├── 04-wordlist-preparation.png
│   ├── 05-john-cli-dictionary-attack.png
│   ├── 06-john-cli-password-recovered.png
│   ├── 07-pdf-password-verification.png
│   ├── 08-jtr-cli-flag.png
│   ├── 09-networkwalks-hash-calculator.png
│   ├── 10-networkwalks-comparison-tool.png
│   ├── 11-networkwalks-password-match.png
│   ├── 12-networkwalks-pdf-verification.png
│   └── 13-networkwalks-flag.png
│
└── notes/
    └── lab-notes.md
```

> Replace the screenshot filenames with the actual files included in your repository. Do not upload sensitive documents, recovered passwords, or complete PDF hashes unless they are explicitly approved for public sharing.

---

# 9. Conclusion

The Week 03 practical provided hands-on exposure to PDF password security and dictionary-based password auditing.

Through John the Ripper CLI, I explored the process of extracting a PDF hash, preparing a wordlist, executing a dictionary attack, displaying the recovered password, and verifying it against the original protected document.

The Networkwalks tools module further demonstrated how hash extraction and dictionary comparison can be performed through a separate workflow.

Overall, the exercise helped connect theoretical concepts such as encryption, hashing, password verification, and dictionary attacks with practical cybersecurity tools.

It also reinforced an important security principle: **the strength and unpredictability of a password play a critical role in protecting encrypted documents.**

---

# 10. Disclaimer

This repository is maintained for educational and documentation purposes as part of the Networkwalks Cybersecurity Internship.

All practical activities were conducted within an authorized learning environment using designated training documents.

The techniques demonstrated here are intended for legitimate password security auditing and awareness. They must not be used to access, analyze, or recover passwords from documents without the owner's permission or appropriate authorization.

---

## 👩‍💻 Author

**Ayesha Kazi**

Cybersecurity Intern | Networkwalks

| Detail | Information |
|---|---|
| Program | Networkwalks Cybersecurity Internship |
| Week | Week 03 |
| Domain | Cybersecurity & Ethical Hacking |
| Practical Topic | PDF Hash Extraction and Dictionary-Based Password Auditing |
| Primary Tool | John the Ripper CLI |

**Repository Purpose:** Documentation of the Week 03 practical implementation, command-line workflow, technical observations, and cybersecurity learnings.
