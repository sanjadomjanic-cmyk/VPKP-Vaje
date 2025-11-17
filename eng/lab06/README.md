# Exercise 6: Personal Identity Management

In the digital world, personal identities are one of the key elements that enable our presence and operation in cyberspace. Passwords and login details are often the only barrier between our data and a potential attacker, so handling them correctly is crucial for individual security.

Unfortunately, using weak, repetitive passwords and neglecting additional security mechanisms such as two-factor authentication (MFA) is still a common practice among users, which poses a great risk.

# 🧪 Personal Identity Management

In this exercise, we will learn basic techniques for securely managing personal identities in cyberspace.

The purpose of this exercise is for students to learn basic good practices in personal identity management. In the first part, we will learn how to create complex and secure passwords and evaluate them with dedicated tools. In the second part, we will perform a practical MFA setup on popular services such as Gmail or Slack and learn how additional security steps significantly reduce the chances of a successful attack. The exercise addresses both the technical and personal aspects of responsible identity management in cyberspace.

## 1️⃣ Introduction: Personal Identity Management

The goal is for us as users to learn how to:  
✅ create secure passwords,  
✅ check their complexity and resistance to attacks,  
✅ set up two-factor authentication (MFA) to better protect our accounts.  

### Personal identities and secure passwords

Every Internet user presents their personal identity in cyberspace. This is all the data that identifies you when using online services: usernames, email addresses, passwords, security questions, profile pictures, phone numbers, even behavioral patterns.

Our identity is often scattered across many different platforms, so protecting it is challenging but extremely important. Misuse of personal identity can lead to data theft, access to bank accounts, the spread of false information in our name, or even blackmail.

The most common way to protect your identity is still passwords, which are the first line of defense against unauthorized access. Unfortunately, research shows that users often use passwords that are too short, simple character sequences, or the same passwords on multiple services. This allows attackers to quickly gain access using dictionary attacks, brute force, or already exposed databases. Therefore, passwords must be long enough, unpredictable, and consist of uppercase and lowercase letters, numbers, and special characters. It is even better if we use a different password for each service and use a password manager to help us with this.

It is also important to understand that no password is completely secure if it is not accompanied by additional security mechanisms. Therefore, whenever possible, we enable two-factor authentication (MFA), which adds another layer of protection — for example, a one-time code that we receive on our phone or generate with an application. This makes it significantly more difficult to attack an account, because the attacker also needs something that we have physically with us.

## 2️⃣ Activity: Using the Bitwarden Password Generator and Strength Evaluator

### 🔐 Password Generator

Set various parameters on the **Password Generator** page and generate one password for each setting.
Copy the passwords as you go and write them down on a sheet of paper or in a document.

### ✅ Examples to create

| Password | Length | Character set |
|------|--------------|-----------------------------------|
| G1 | 8 characters | only letters (lowercase and uppercase) |
| G2 | 12 characters | letters + numbers |
| G3 | 16 characters | letters + numbers + special characters |
| G4 | 24 characters | anything |
| G5 | Passphrase | 4 words (separated by spaces or dashes) |

Check each of the passwords above on the **Password Strength Tester** page.
For each password, write down a score:

color indicator (e.g. red, orange, green)

estimated number of years to crack (if shown)

### 📝 Analysis and report

For each password, write down:
- The password you created.
- What settings you chose.
- Is the password safe to use and what would you change to make it even more secure?

  Password: Computer, length: 8 characters, character set: only letters (lowercase and uppercase), password strength: very weak, estimated time to crack : less than a second.
  
  Password: 12Computer34, length: 12 characters, character set: letters + numbers, password strength: weak, estimated time to crack : 3 hours.
  
  Password: 12Computer34!!!!, length: 16 characters, character set: letters + numbers + special characters, password strength: good, estimated time to crack : 1 month.
  
  Password: !!!!12.Com+Put+Er.34!!!!, length: 24 characters, character set: anything, password strength: strong, estimated time to crack : centuries.
  
  Password: My-computer-is-great, character set: 4 words,  password strength: good, estimated time to crack : 8 years.
  
The password becomes safer with every additional character and by adding numbers and special characters.

## 3️⃣ Reflection and analysis

- How does the security score increase as you add length?

Password security increases exponentially as length grows. With every extra character multiplies the number of possible combinations, making the password dramatically harder to crack.
  
- How do special characters affect the score?

  Special characters increase the password score by adding more possible character choices and making the password harder to guess through brute force or pattern-based attacks.
  
- How does a “passphrase” score compare to a classic password?

A passphrase usually scores higher than a traditional password because it is typically longer, even if it contains mostly normal letters. The length provides exponential security, making it harder to crack through brute-force attacks

- Which password would you recommend for everyday use and why?
  
I would recommend using a passphrase because it is generally more secure than classic passwords and easier to remember.


## References

1. OpenAI. (2025), *ChatGPT* (Aug 2025) [Large language model], https://chat.openai.com/
