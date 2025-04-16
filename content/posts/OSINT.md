+++
title = "OSINT"
date = 2025-04-16T15:06:31+02:00
draft = false
+++
# OSINT Tools & methods 
## ⚠️ Disclaimer

This repository is intended **for educational purposes only**.

All tools, techniques, and information provided here are meant to help individuals:

- Understand open-source intelligence (OSINT)
- Improve personal and organizational cybersecurity awareness
- Explore ethical and legal methods of online investigation

> **Use responsibly.**

The authors and contributors do **not condone** or support:
- Unlawful surveillance or harassment
- Unauthorized data collection or access
- Any use of this code or information that violates local, national, or international laws

By using this repository, you agree to use it **only within legal boundaries** and for **ethical research or educational objectives**.

**We take no responsibility** for any misuse or illegal activity carried out with the help of this project.

## Quick overview of OSINT Tools & Methods
### Basic pillars of OSINT:
| Technique  | Purpose  |
| ------------ | ------------ |
| Passive Reconnaissance  |  Gathering data without interacting with the target |
|  Cross-Correlation | Linking data points across platforms (e.g., username ↔️ email ↔️ photo)  |
|  Fingerprinting & Patterns |  Habits, posting styles, time zones |
| Pivoting  |  Using one data point (e.g. email) to find others (username, profiles, leaks) |
|  Metadata Extraction |  Reading hidden data in files, images, documents |
| Google Dorking  | Crafting precise search queries to find open data  |
###Tools to use 
 - **MetaData Extraction From files :** Exiftool
 - **Data Leaks (Emails & Passwords):**  [HaveIBeenPwned](https://haveibeenpwned.com/)
 - **Finding Emails From Domains (Freemium but excellent) :** [hunter.io](https://hunter.io/)
 - **Holehe -- Account checking on 50+ sites using email : ** [holehe](https://github.com/megadose/holehe.git)
 - **Risk score checking and finding linked accounts : ** [emailrep.io](https://emailrep.io/)
 - **Search engine for devices connected to internet : ** [shodan.io](https://www.shodan.io/)
 - **Owner information & registration history : ** [whois](https://www.whois.com/whois/)
---
## Methods and how to
###Google Dorking
Google Dorking is used to search for exact information on sites with usage of symbols in your search query:
 - `site`:  -- used for search only on site 	(example: ```site:github.com```)
 - `inurl`: -- searching for keywords in url (example ```inurl:admin```)
 - `intitle`: -- Search in page title
 - `filetype`: -- searching for specific filetype(example ```filetype:pdf```)
 - `ext` -- searching for specific extension(example ```ext:.docx```)
 - `cache:` -- View google's cached version
 - `related`: -- Show related Websites
 - `*` -- Is Wildcard showing flexible matching
 - OR / AND -- Booleans to make combos with dorks
 - `" "` -- searching for exact match
 ---
 Now i will show you some examples & also how to combo these dorks for effective searching:
 ```bash 
inurl:admin login
intitle:"index of" admin
site:*.gov inurl:login
```
First row will show you only urls that have admin like https://admin.microsoft.com/AdminPortal/Home
Second row will show you only Titles that have word admin mentioned in them
Third row is little bit complicated so break it up first part is searching for all sites (`*`) ending on .gov and link need to have login mentioned

```
site:pastebin.com intext:"@gmail.com" AND password
```
This will search only pastebin site use intext dork to search `<body>` element of HTML for exact phrase that is @gmail.com and password which of course is changed and tailored for the user needs


