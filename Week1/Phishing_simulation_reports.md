# Phishing

It is an attack that attempts to steal money, identity by making users reveal personal information such as cerdit card number, bank information or password on websites that pretend to be legitimate.

Although Bhutan is not far into cyber world, Bhutan alone has recorded 96 cases of pyramid schemes and online scam in four years between 2022 to May 2024. (Source- Kuensel, June 3rd 2024)

## What is Phishing Simulation?

Phishing simulations are controlled, mock phishing attacks conducted by organizations to test and improve their employee's cybersecurity awareness.

Phishing simulations are an important tool in cybersecurity training, helping organizations strengthen their first line of defense against real phishing attacks.

# Phishing Simulation Tools

## Black Eye

Blackeye is an open-source phishing toolkit used for social engineering attacks. It automates the process of creating phishing web pages that resemble legitimate websites, aiming to trick users into revealing sensitive information like credentials or personal data. Here’s an overview:

### Key Features
1. **Pre-Built Templates**: Blackeye includes over 30 ready-made phishing templates for popular platforms such as:
   - Social Media: Facebook, Instagram, Snapchat, LinkedIn.
   - Email Services: Google, Yahoo, ProtonMail.
   - Streaming Platforms: Netflix, Spotify.
   - Gaming and Development: Steam, GitHub.
   - Productivity Tools: Microsoft, WordPress.

---
2. **Custom Templates**: Users can create and deploy their own templates for more targeted attacks, increasing its adaptability.

3. **Ease of Use**: Blackeye simplifies phishing by providing pre-configured scripts and templates, reducing the need for extensive technical expertise.

4. **Social Engineering Focus**: It helps attackers craft convincing fake emails or websites to lure victims, leveraging human psychology rather than technical vulnerabilities.
---
### Functionality
- **Phishing Web Pages**: Mimics login pages of legitimate sites to harvest credentials.
- **Phishing via Social Media**: Targeted phishing through platforms like Instagram and Facebook.
- **URL Masking**: Uses techniques to obscure phishing URLs, making them appear legitimate.

---

### Defense Strategies
- **Awareness Training**: Educate users to identify phishing attempts, such as checking URLs and email authenticity.
- **Anti-Phishing Tools**: Employ browser extensions or software that detect and block phishing attempts.
- **Two-Factor Authentication (2FA)**: Add a layer of security that mitigates the impact of credential theft.

---

#### Installation

1. git clone from https://github.com/shuvo-halder/blackeye

2. cd blackeye

3. bash blackeye.sh

![alt text](<Images/Screenshot from 2024-11-21 17-42-23.png>)

We get the options to choose for the platform to use in order to fetch user credentials.


## Zphisher

**Zphisher** is an open-source phishing toolkit widely used for simulating phishing attacks. It simplifies the process of creating and hosting phishing websites designed to trick users into revealing sensitive information such as login credentials. 

---

### Key Features
1. **User-Friendly**: Zphisher is known for its ease of use, making it more accessible than tools like the Social Engineering Toolkit (SET).
   
2. **Pre-Built Templates**: Offers over 30 phishing templates for popular platforms, such as:
   - **Social Media**: Facebook, Instagram, Snapchat, LinkedIn.
   - **Email Providers**: Google, Yahoo, ProtonMail.
   - **Streaming Services**: Netflix, Spotify.
   - **Development/Gaming**: GitHub, Steam.
   - **Business Platforms**: Microsoft, WordPress.

3. **Custom Templates**: Users can design their own phishing templates to meet specific attack scenarios.

4. **Wide Area Network (WAN) Support**: Facilitates phishing campaigns that work over the internet, not just local networks, making it capable of targeting remote users.

5. **Credential Harvesting**: Designed to collect sensitive user data like login IDs and passwords when victims interact with the phishing pages.

---

### How It Works
- **Phishing Pages**: Zphisher hosts fake login pages that resemble legitimate websites.
- **URL Masking**: Employs techniques to obscure the actual phishing URL, making it appear genuine.
- **Cross-Network Usage**: Can operate over WAN for a broader reach, using tools like Ngrok or Serveo to expose local servers to the internet.


---

### Defense Against Phishing
1. **User Education**: Train users to identify suspicious URLs and emails.
2. **2FA (Two-Factor Authentication)**: Adds an extra layer of security beyond credentials.
3. **URL Verification**: Encourage users to verify web addresses carefully before entering personal information.
4. **Anti-Phishing Solutions**: Use security software to detect and block phishing attempts.

---

**Note**: If you are exploring tools like Zphisher, ensure that you use them responsibly, strictly for educational purposes, or with explicit permission during penetration testing engagements. Misuse can lead to severe legal consequences.

---
#### Installation

1. git clone from https://github.com/Exido-Rio/zphisher-

2. cd zphisher

3. bash zphisher.sh

![alt text](<Images/Screenshot from 2024-11-21 18-05-12.png>)