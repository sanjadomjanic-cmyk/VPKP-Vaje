# Exercise 7: Using Secure Communication

In our daily lives, we communicate via email, chat apps, and social media. Most of this communication is not protected, so it can be intercepted by anyone between the sender and the recipient.
**Encryption** ensures that only the intended recipient can read the message, and prevents eavesdropping, manipulation, and data theft.

In this exercise, you will work in a **realistic scenario** and use **PGP for email encryption** and **Signal for secure messaging**.

---

## 🎯 Scenario
Imagine you are a journalist talking to a whistleblower from a company.
You receive sensitive documents and you need to make sure that:
1. No one else will be able to read the contents.
2. The document will be confirmed to have come from the right person.
3. The sender and recipient will be able to make sure that no third party has interfered between them.

---

## 1️⃣ Introduction to encryption

- **Symmetric encryption** – the same key for encryption and decryption (e.g. AES).
- **Asymmetric encryption** – a public/private key pair (e.g. RSA, ECC).
PGP (Pretty Good Privacy) uses this principle.
- **Digital signature** – you sign a message with a private key, and the public key allows authentication.

---

## 2️⃣ Vulnerability simulation
First, we will demonstrate the vulnerability when using unencrypted connections using the example of a test SMTP server.

1. Connect to a **test SMTP server** (can be local) and send an email without encryption.
2. Use **Wireshark** or `tcpdump` to show that the content is visible in “cleartext”.
3. Write down your findings – what risks this would pose in the real world.

This tutorial shows how to capture **cleartext** SMTP traffic in a Google Cloud Shell environment and analyze it in Wireshark.
We will use MailHog as a test SMTP server and `swaks` to send a test message.

---

### Running MailHog in GitHub Codespaces

```bash
sudo apt-get update
sudo apt-get install -y docker.io
sudo docker run -d --name mailhog -p 1025:1025 -p 8025:8025 mailhog/mailhog

```

- SMTP: `127.0.0.1:1025` (without TLS)
- UI: Web Preview → Port 8080

---

### `tcpdump` capture

```bash
sudo apt install tcpdump
sudo tcpdump -i any tcp port 1025 -w smtp.pcap &
```

- `&` sends the process to the background so you can run `swaks` in the same terminal.

---

### Sending a test message with **swaks**

```bash
swaks --server 127.0.0.1 --port 1025 --from ti@example.com --to test@example.com --data "Subject: Codespace SWAKS Test\n\nGreetings from FIS!"
```

- Since MailHog doesn't have TLS, `swaks` will not encrypt — the traffic will be seen as *cleartext*.

---

### Stop the capture

```bash
sudo pkill tcpdump
```
*(or **Ctrl + C** if `tcpdump` was not running in the background)*

---

### Download `.pcap` to your local computer

- In the Codespace panel, find `smtp.pcap`
- Right-click → **Download**
- Open the file in Wireshark.

---

### Analysis in Wireshark

1. Filter:
```
tcp.port == 1025
```
2. Click on the packet with `DATA` in the **Info** column.
3. Right-click → **Follow → TCP Stream**.
4. In a new window you can see the entire SMTP session:
- SMTP commands (`EHLO`, `MAIL FROM`, `RCPT TO`)
- Email headers (`Subject: ...`)
- Email body

---

## 3️⃣ Activity: Encrypted communication

### Capturing and analyzing encrypted SMTP traffic

This exercise shows how to capture **cleartext** SMTP traffic in a Google Cloud Shell environment and analyze it in Wireshark.
We will use MailHog as a test SMTP server and `swaks` to send a test message.

### Installing Postfix

```bash
docker run -d --name postfix587 -p 587:587 -e ALLOWED_SENDER_DOMAINS="localdomain" -e POSTFIX_myhostname=postfix.local boky/postfix
```

---

### Capture with `tcpdump`

```bash
sudo tcpdump -i any tcp port 587 -w smtpssl.pcap &
```

- `&` sends the process to the background so you can run `swaks` in the same terminal.

---

### Sending a test message with **swaks**

```bash
swaks --server 127.0.0.1 --port 587 --tls --from test@localdomain --to demo@localdomain --header 'Subject: STARTTLS test' --body 'Hello via TLS!'
```
---

### Stop the capture

```bash
sudo pkill tcpdump
```
*(or **Ctrl + C** if `tcpdump` was not running in the background)*

---

### Download `.pcap` to your local computer

- In the Codespace panel, find `smtpssl.pcap`
- Right click → **Download**
- Open the file in Wireshark.

---

### Analysis in Wireshark

1. Filter:
```
tcp.port == 587
```
2. Click on the packet with `DATA` in the **Info** column.
3. Right click → **Follow → TCP Stream**.
4. In a new window, you can see the entire SMTP session with encrypted content.

---

## 5️⃣ Reflection

- How would you explain the difference between an unencrypted (e.g. SMTP without TLS on port 1025) and an encrypted message (SMTP with STARTTLS on port 587)? What data can an attacker see in the first case and what in the second?

  With unencrypted SMTP (port 1025), an attacker can read the entire email. All communication is sent in cleartext. An attacker can see SMTP commands, sender and recipient addresses, email headers (subject) and the full   email body.
  With SMTP using STARTTLS (port 587), the communication is protected by TLS encryption. The attacker sees only connection metadata (IP addresses, ports, and that a TLS connection is used), not the message itself, not     even the headers.
  
- Why is fingerprinting in PGP to prevent man-in-the-middle attacks?

  PGP fingerprinting prevents man-in-the-middle attacks by allowing users to verify that a public key truly belongs to the intended person and was not replaced by an attacker.
  
- When would you use PGP and when would you use Signal?
  
  PGP is used for secure email and files, while Signal is used for real-time encrypted messaging and calls.
  
- Do you think end-to-end encryption should be the default in all communication applications?
Justify your answer from the perspective of security, privacy, and user experience.

Yes, end-to-end encryption should be the default because it protects security and privacy while keeping the user experience simple by requiring no extra action from users.

---

## References

1. Boky, Postfix Docker image, https://hub.docker.com/r/boky/postfix
2. MailHog, MailHog email testing tool, https://github.com/mailhog/MailHog
3. Docker Inc., Docker – Empowering App Development, https://www.docker.com/
4. Tcpdump Group, tcpdump, https://www.tcpdump.org/
5. Jetmore, J., swaks – Swiss Army Knife for SMTP, https://github.com/jetmore/swaks
4. OpenAI. (2025), *ChatGPT* (Aug 2025) [Large language model], https://chat.openai.com/
