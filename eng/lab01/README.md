# Exercise 1: Individual Security in Cyberspace

We use cyberspace every day. Examples of cyberspace usage include communication, shopping, banking, as well as work and entertainment. Individuals are users of cyberspace, but at the same time they are also targets and we are often unaware of all the dangers and consequences of our actions.

The aim of the exercises in the course Individual Security in Cyberspace is to introduce students to key concepts of cybersecurity from an individual perspective, develop a sense of risks and vulnerabilities, and equip them with basic knowledge for safer use of modern technologies.

# 🧪 Let's get to know cyberspace

The first exercise is intended to introduce cybersecurity and to learn about basic concepts and challenges:

- Who or what is an individual in cyberspace?

- What does the term cyberspace mean and how do we perceive it?

- What do we understand by the term cybersecurity?

## 1️⃣ Introduction: Analysis of personal exposure in cyberspace

Exercise objectives:  
✅ To learn the basic concepts: individual, cyberspace cybersecurity, privacy.  
✅ To recognize personal data and how it is accessible in the online environment.  
✅ To understand how modern technologies affect the security and privacy of an individual.  

### Security and privacy

An individual in cyberspace is any user of technologies and devices that are connected to a network and use Internet services.

Security:
Security (cybersecurity) encompasses the protection of ICT systems, networks and data from unauthorized access, attacks, failures or misuse. The purpose is to ensure the confidentiality, integrity and accessibility of data and services.
Example: to prevent hacking into a user's email account.

Privacy:
Privacy concerns the right of a person to have control over their personal data and the way in which it is collected, used, disclosed or stored. It's about how much information a person wants to reveal about themselves and to whom.
Example: the right for a web platform not to share user data with advertisers without consent.

## 2️⃣ Activity: Personal Exposure Analysis

Open the incognito/private mode in your browser and search for information about yourself (e.g. via search engines and exposure checking services):
- Search for your first and last name on Google.
- Check any public profiles (Facebook, LinkedIn, Instagram, forums).
- Use exposure checking tools (HaveIBeenPwned, OSINTLeak)
- Tools: PimEyes, haveibeenpwned, OSINTLeak

### Google dorking/hacking

Google Dorking (also known as Google Hacking) is a method that exploits advanced search operators in Google (or other search engines) to obtain data that is not intended for the public, but is still available online.

It is the exploitation of a misconfigured website, servers or applications where files, documents or even passwords are accessible to the public but hidden from ordinary users.

Google Dorking is not illegal as long as we do not interfere with protected systems. However, the information found must not be misused, stored without permission or disclosed publicly.

### 📘 Examples of Google Dork search queries

| Search query | What does it find? |
|---------------------------------------------|---------------------------------------------------|
| `filetype:pdf site:gov.si` | PDF documents on Slovenian government websites |
| `intitle:"index of" passwords` | Folders with the name "index of" and files with passwords |
| `inurl:admin login` | Pages with the option to log in to the administration |
| `site:pastebin.com password` | Posts with passwords on Pastebin |
| `"confidential" filetype:pdf` | Documents marked "confidential" in PDF format |
| `ext:sql intext:"password"` | Public SQL files containing passwords |
| `intitle:"webcamXP 5"` | Unprotected IP camera interfaces |
| `inurl:/phpinfo.php` | Public PHP configuration files |
| `filetype:env intext:DB_PASSWORD` | Public `.env` files with database passwords |
| `site:*.* inurl:/config.json` | Public application configuration files |

## 3️⃣ Reflection and analysis

- Write a short report on what data you found.
  
In my browser's private mode, I found informations about my thesis, my workplace and deatails about my dog. On facebook, I found one user with the same name as mine. With exposure-checking tools, I discoverd that one of my email accounts had been involved in 1-2 data breaches, and the second one appeared in 9-13, depending of the tool used. 
With PimEyes, I found photo of me on my workplace's website of and another photo of me on a website that was unfamiliar to me. 
  
- What potential risk does it pose?
  
The data-breach results show that my email addresses have been exposed multiple times, which increases the risk of password leaks, unauthorized logins, identity theft, and spam.
The images found via PimEyes could be misused to create fake profiles, impersonate me,  or track my online presence without my consent.

- Write a worst-case scenario example of how someone could benefit from this data in the event of personal exposure.
A malicious actor could combine my leaked email data with publicly available information about my workplace and personal life to craft a convincing spear-phishing attack. Using my exposed photos, they could create a fake social-media profile that appears authentic. They might impersonate me to contact my colleagues or friends, asking for sensitive information or financial transfers. With access to my breached email credentials, they could even gain entry to my real accounts, further strengthening the impersonation. This could lead to identity theft, financial loss, and reputational damage.
 
- How would you rate your personal security/privacy?

I would rate my current personal security and privacy as moderate, as my accounts and identity could still be vulnerable unless I strengthen my security habits, such as improving password security practices, enabling two-factor authentication, and limiting the amount of personal information I share online.

## References

1. PimEyes., *Face recognition search engine*, https://pimeyes.com/
2. Have I Been Pwned, *Data breach search and notification service*, https://haveibeenpwned.com/
3. OSINT Framework, *OSINT tools and resources collection*, https://osintframework.com/
4. OpenAI, (2025), *ChatGPT* (Aug 2025) [Large language model], https://chat.openai.com/
