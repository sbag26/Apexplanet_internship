Cybersecurity Basics

The CIA Triad is a foundational model in information security designed to guide policies for
protecting an organization's data, systems, and network resources.
The Three Pillars
Confidentiality
What it means: Keeping sensitive data secret and preventing unauthorized viewing,
exposure, or theft.

Common controls: Encryption (such as AES or RSA), multi-factor authentication (MFA), role-
based access controls (RBAC), and data classification.

Integrity
What it means: Ensuring data is trustworthy, accurate, and completely free from
unauthorized tampering, alteration, or corruption.
Common controls: Cryptographic hashing, digital signatures, checksums, audit logs, and
version control.
Availability
What it means: Guaranteeing that authorized users can access systems, networks, and data
whenever they need them without disruption.
Common controls: Redundant hardware, failover systems, regular backups, disaster
recovery plans, and DDoS mitigation.
Why It Matters
The model acts as a core checklist when evaluating vulnerabilities, designing new security
projects, and responding to cyber incidents. It is explicitly referenced in major international
standards and compliance frameworks like ISO/IEC 27001 and the GDPR.

Cyber Threat Types :
1. Phishing
What it is: A social engineering attack that tricks people into giving up private data like
passwords or credit card numbers.
How it works: Attackers send fake emails, text messages, or links to spoofed websites that
look like trusted companies.
CIA Triad impact: Breaks Confidentiality by exposing private credentials.
Key defenses: User awareness training, email spam filters, and Multi-Factor Authentication
(MFA).

2. Malware (Malicious Software)
What it is: Any harmful software built to infiltrate, damage, or take control of a computer
system.
Common forms:
Viruses attach to normal files and spread when a user opens them.
Worms self-replicate and spread across networks on their own.
Trojans hide inside fake, useful-looking programs to trick users into installing them.
CIA Triad impact: Threatens Confidentiality, Integrity, and Availability depending on the
software's goal.

Key defenses: Antivirus software, regular system updates, and blocking untrusted
downloads.

3. DDoS (Distributed Denial-of-Service)
What it is: An attack meant to crash a website, server, or network so real users cannot
reach it.
How it works: Attackers use a large network of hacked devices (a botnet) to flood a target
server with overwhelming traffic.
CIA Triad impact: Directly destroys Availability.
Key defenses: Traffic filtering (scrubbing), Web Application Firewalls (WAFs), and rate
limiting.

4. SQL Injection (SQLi)
What it is: A web attack that targets the database behind a website or app.
How it works: Attackers type malicious database commands into poorly protected input
boxes (like login forms or search bars) to view, change, or delete records.
CIA Triad impact: Breaks Confidentiality (data theft) and Integrity (data tampering).
Key defenses: Parameterized queries (prepared statements), strict input validation, and
firewalls.

5. Brute Force Attack
What it is: A trial-and-error method used to crack passwords, PINs, or encryption keys.
How it works: Automated software rapidly tests millions of character combinations until it
finds the right login credentials.
CIA Triad impact: Breaks Confidentiality by gaining unauthorized account access.
Key defenses: Account lockout limits after failed attempts, MFA, CAPTCHA, and long
complex passwords.

6. Ransomware
What it is: A specialized type of malware designed for digital extortion.
How it works: Once inside a system, it encrypts the victim's files so they cannot be opened,
then demands a ransom payment for the decryption key.
CIA Triad impact: Blocks Availability (locking files) and often threatens Confidentiality
(threatening to leak stolen data).
Key defenses: Offline backups (3-2-1 backup rule), endpoint protection, and keeping
software patched.

Quick Revision Summary
Human-focused attacks: Phishing and Trojans rely on tricking users into making mistakes.
Technical-focused attacks: SQL Injection, Brute Force, and DDoS exploit system flaws,
weak passwords, or network limits.

Best overall habit: Combining MFA, regular software updates, and offline backups
stops the vast majority of these attacks.
Attack Vectors :

1. Social Engineering
What it is: The art of manipulating human psychology to trick people into handing over
confidential information or granting system access.
How it works: Attackers exploit trust, fear, urgency, or curiosity rather than using technical
software exploits. Common examples include phishing emails, pretexting (inventing a fake
scenario), and tailgating (following an employee into a restricted building).
CIA Triad impact: Primarily breaks Confidentiality by tricking users into revealing
passwords or sensitive files.
Key defenses: Regular security awareness training, strict identity verification rules, and
Multi-Factor Authentication (MFA).

2. Wireless Attacks
What it is: Exploiting weaknesses in wireless networks (such as Wi-Fi or Bluetooth) to
intercept data or gain unauthorized network entry.
How it works: Attackers crack weak Wi-Fi passwords, spy on unencrypted public traffic, or
set up fake Wi-Fi hotspots (known as Evil Twin attacks) to trick users into connecting to their
device.
CIA Triad impact: Threatens Confidentiality (eavesdropping on traffic) and Integrity
(altering data sent over the network).
Key defenses: Strong encryption protocols (WPA3), complex Wi-Fi passwords, disabling
auto-connect on devices, and using a Virtual Private Network (VPN) on public networks.

3. Insider Threats
What it is: A security risk originating from inside the organization, involving current or former
employees, contractors, or business partners who already have authorized access.
How it works: Insiders misuse their legitimate credentials to steal trade secrets, leak
customer records, or sabotage systems. This can be malicious (intentional theft or revenge) or
accidental (carelessly mishandling sensitive files).
CIA Triad impact: Can compromise Confidentiality (data leaks), Integrity (altering
company records), and Availability (deleting critical files).
Key defenses: Applying the Principle of Least Privilege (giving users only the access they
need), monitoring user activity logs, and immediately revoking accounts when employees leave.

Quick Revision Summary
Attack Vectors vs. Threat Types: An attack vector is the path an attacker takes to get in
(like a fake Wi-Fi network), while a threat type is the weapon or action used once inside (like
ransomware).
External vs. Internal paths: Social engineering and wireless attacks usually come from
outside the organization, while insider threats exploit trusted access from within.
