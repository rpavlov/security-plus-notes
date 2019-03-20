# Identifying Threats & vulnerabilities

## Social engineering

Non-technical attack. Usually via email or phone. Types include:

Spoofing (desiign email to appear like its coming from trusted party), phishing (fake website/markup), url hijacking/typo squatting, dumpster diving, tailgaiting, shoulder surfing, impersonation.

Main ones are spoofed email and phishing website. emkei.cz is a fake email generator.

SET=social engineering toolkit is a popular choice. You can perform credential harvesting with phished sites.

Security awareness training helps mitigate social engineering risk. This puts responsibility on the employee, and should be an instructor-led training. No one reads long emails/documentation.

## Malware

Viruses, worms, adware, spyware, trojans, rootkits, logic bombs, ransomeware. Generally falls into two types: spyware and damaging applications.

## Software based threats

Dictionary, brute-force, guessing and rainbow table are password cracking methodologies. There are sites/dumps with default credentials based on device (ex. routers) which help with this.

## Rainbow tables

Cheaper than a brute-force, which has to waste computation on calculating a hash on each attempt.

This is usually done against a dump of encrypted passwords. It attempts to reverse the hash. Additionally, it's necessary to figure out the type of hashing algorithm used, MD5, lm, fastlm etc.

Adding a salt to the hash function makes this infeasable.

## Network based threats

## Wireless based threats

## Physical threats