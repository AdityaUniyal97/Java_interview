 ## **What is Netwrok Security**?
Network security is a set of strategies and technologies which are designed to protect the network and data from cyber threats . It ensures a secure communication and data transfer over the network ,preventing the unauthorized access to the data.
**Importance of Network Security**
- Prevents the unauthorized access to the data
- Protection against cyber threats like hacking , malware and phising.
- Ensure data confidentiallity , integrity and availability 

## **Goal of a Network Security**
Network security aims to achieve the CIA triad .
**Confidentiality**
- Ensures  that the data is accessbile to only authorized users.
- Protects the sensitive information from unautorized access.
- Implemented through encryption , access control  and authentication mechanism 
**Integrity**
- Ensures that the data remain accurate and unchanged during the transmission and storage
- Prevents the unauthrized modification , deletions .
- Implemented using Hashing , digital signature and checksum.
**Availability**
- Ensures that the network resources are availabale when ever we needed
- Protect agains DOS(Denial of Service) attack and system failures.
- Implemented thorugh load balancing , firewall .

## **ISO Security Architecture**
$$
              +---------------------------------+
              |        ISO Security Architecture       |
              +---------------------------------+
                                |
  -------------------------------------------------
  |                      |                      |
Security Attacks   Security Services   Security Mechanisms
  |                      |                      |
  |                      |                      |
  |                      |                      |
+----------------+   +----------------+   +----------------+
| Passive Attacks  |   | Confidentiality  |   | Encryption        
| - Eavesdropping  |   | Integrity        |   | Digital Sig
| - Traffic Analysis| | Authentication   |   | Firewalls          |
+----------------+   / Access Control /   / IDS (Intrusion  /
                    | Non-repudiation |   | Detection System) |
                            +----------------+   +----------------+
  |
+----------------+
| Active Attacks  |
| - Masquerade    |
| - Replay Attack |
| - Modification  |
| - DoS Attack    |
+----------------+

$$
The ISO Security Architecture is a part of the ISO 7498-2 standard and define the rules for secure communication over the network . It helps protects data from cyber threats.
**Key Components of ISO Architecture**
1. Security Attacks(Threats to network security)
2. Security Services(Measures to protect the network)
3. Security Mechanism(Techniques used to implement security serivces)

<u><b>Security Attacks</b></u> 
Attack on Network can be divided into two types :
*1)Passive Attacks :* 
- The attacker secreatly listens to the communication
- No changes are made to the data , so they are hard to detect
- Example :
    . EavesDropping - Listening to private conversations
    . Traffic Analysis - Studing message flow to learn useful  deatils.
*2)Active Attacks :*
- The attacker modifies or disrupts the data.
- These attack are easy to detect but causes serius harm
- Example :
    - Denial of Service(DOS) - A system is floaded with requests to make it stop working

<u><b>Security Services</b></u>
ISO defined six security service to protect the data and network.
1. <u>Autherntication</u> : Ensures that the users and the devices are the same which they are claiming . 
   Example - Passwords , BioMatrics.
2. <u>Access Control :</u> Prevents unauthorized access to the data . 
   Example - Firewall , permissions
3. <u>Data Confidentialty :</u> Keep the information private and protected.
   Example - SSL , VPN
4. <u>Data Integrity :</u> Ensures tha the data us not changed or corrupted
   Example - Hashing , CheckSum
5. <u>Non-Repudation :</u> Prevents the user from denying their actions
   Example - Digital Signature
6. <u>Availability :</u> Ensures that data and the services are accessible whenever needed. Example - Backups. 

<u><b>Security Mechanisms</b></u>
Security Mechanism helps to enforce the security services .
- <u>Encryption :</u> Converting the data into unreadable formor scarambled form for unauthorize user
   Example - RSA , SSL encryption
 - <u>FireWalls :</u> Blocking unauthorize access to networks.
   Example - Window Defender Firewall
 - <u>Intrusion Detection System</u> Detects and alerts on suspicius activity 
   Example - Snort
 - <u>Digital Signature :</u> Confirms the senders authenticity and ensure data integrity
 - <u>Access Control List(ACLs) :</u> Defines which user can acces the specific resources
 - <u>Authentication Protocols :</u> Verifies the user identity

# **Categories of Attacks**
Network attack can be categorized into different attacks based upon their impact. Major Types of Attacks are:
**1) Interuption(Denial Of Service -DOS Attack)** 
- The attacker distrupts the service making it unavailable.
- Example = DOS/DDOS Attack - Flooding a website with too many request to crash it
- Impact : Prevent the legit user from accessing the services
 **2) Interception(Unauthorized Access)**
- The attacker secreatly captures the network traffic
- Example Evesdropping  , man in the middle attack , Packet Sniffing
- Impact : Sensitive data like passwords and credit card details can be stolen
**3) Modification(Altering Data)**
- The attacker change or manipulate the data during transmission
- Example Man in the middle attack , Replay attack
- Impact : Messages are being changes which leads to missinformation and fraud
**4) Fabrication(Fake Data Injection)**
- The attacker creates and sends the false infromation into the system
- Example Email Spoofind , Phising attack
- Impact : Users are being tricked to belived in the false information 

# **Network Seurity  Services & Mechanisms** 
Network Security serivces and mechanisms work together to protect data from attakcs.
**1. Network Security Services**
ISO defined six security service to protect the data and network.
1. <u>Autherntication</u> : Ensures that the users and the devices are the same which they are claiming . 
   Example - Passwords , BioMatrics.
2. <u>Access Control :</u> Prevents unauthorized access to the data . 
   Example - Firewall , permissions
3. <u>Data Confidentialty :</u> Keep the information private and protected.
   Example - SSL , VPN
4. <u>Data Integrity :</u> Ensures tha the data us not changed or corrupted
   Example - Hashing , CheckSum
5. <u>Non-Repudation :</u> Prevents the user from denying their actions
   Example - Digital Signature
6. <u>Availability :</u> Ensures that data and the services are accessible whenever needed. Example - Backups. 
**2. Network Security Mechanism**
Security mechanism helps to apply the securty service effiectively
 - <u>Encryption :</u> Converting the data into unreadable formor scarambled form for unauthorize user
   Example - RSA , SSL encryption
 - <u>FireWalls :</u> Blocking unauthorize access to networks.
   Example - Window Defender Firewall
 - <u>Intrusion Detection System</u> Detects and alerts on suspicius activity 
   Example - Snort
 - <u>Digital Signature :</u> Confirms the senders authenticity and ensure data integrity
 - <u>Access Control List(ACLs) :</u> Defines which user can acces the specific resources
 - <u>Authentication Protocols :</u> Verifies the user identity

## Kerberos
Kerberos is a network authentication protocol thaht uses ticket to verfies the user . It was developed by MIT and widely used in WIndows , Linux and Unix system.
**Componenets of Kerberos**
1. Key Deistribution Center (KDC) = This is the main server that manages the authentication
2. Authentication Server(AS) = Verifies the user identity and issues a Ticket Granting Ticket(TGT)
3. Ticket Granting Server(TGS) = Provide service ticket to access specific resources.
**Working of Kerberos**
- The users sends a login request to the AUthentication Server(AS)
- AS verifies user and issues a Ticket GRanting Ticket(TGT)
- The user than send its TGT to the Ticket Granting Server(TGS) to get a service ticket
- TGS issues a  serivce ticket that allow the user to access the service
**Advantage of Kerberos**
- No password are sent over the network
- Protectiong agains eves dropping , and replay attack
**Disadvantage of Kerberos**
- Requires the time synchronization between the servers.
- If the Key Distribution Center(KDC) fails than authentication is not possible

## **X.509 Authentication**
X.509 is a digital certificate-based authentication system which is use to verifiy the user identity online . Is is a part of a public key infrastructure(PKI) and is commonly used in SSL , TLS , HTTP etc
**How X.509 work**
- A certificated Authority(CA) issues a digital certificate to  user 
- The certificate contains : 
         - User identity(name , email etc)
         - Public Key(for Encryption)
         - CA digital Signature to proof the certificate valid
- When user visits a website than the server presents its own X.509 certificate
	- Now the User system verifies the certificate using the CA digital signature
- If the certificate is valid a secure connetion is established
**Advatange**
- Provide strong security using the public key
- Used in Secure Websites , emails and VPNS
**Disadvatnage**
- Require trusted certificate Authorities(CAs)
- Managing certificates can be complex task.

## **Unit 2**
## **What are Security Threats ?**
Security Threats are the risks that can harm a network , system or data . They try to block , steal or damage the information.
**Common Secrutiy Threats**
- Phising = Fake emails websites which tries to trick the user into sharing the passwrods
- Malware = Harmfull softwares , like viruses , worms that damage the system.
- Denial of Services(DOS) = Flooding a website with too many request to crash it
- Man in the Middle Attack = Hacker secreatly listens the communication between two user
- SQL Injection = A hacker inject a harmful SQL code to steal or modify the data.
**Ways to Protect against the Threats**
- Encryption = Converting the data into scrumbled form so that the unauthorized user cannot read it
- Firewall  = Blocks the unauthorized acces to the netowrk
- Antivirus = Detect and remove the harmfull softwares .
- Multi - Factor Authentication(MFA) = Adds extra security like OTP and the Biomatrices
- Secure Protocols = Use protocols like HTTPS , SSl , TLS and VPN to have secure communication

## **What is SET**
SET(Secure Eltronic Transaction) is a security protocol which is developed by visa and master card to make online credit cards payment secure. 
It ensures that :-
- Customer details remains private
- Transactions are safe from the hacker
- Merchant can verify the cardholder authenticity
**How Set works.**
1. Customer places a order = Buyer selects the product and choose to pay with a credit card
2. Encryption of payment detail = SET encrypt the credit card information before sending it
3. Merchants Forward the details to the bank = The seller cannot see the actual credit card number instead they recive an encrypted payment tokken
4. Bank Verifies transaction = The curtomer bank check if they have enough balance .
5. Payment is approved = If valid the bank approved the payment and transaction in complete.
**Features of a SET PRotocol** 
- Uses Encryption = Keep the credit card deatils private
- Uses digital Signature = Varifies the buyer and sender identity
- Prevent Frud = Merchant dont see the credit card details
- Secure payment = Ensure safe transaction

# **Electronic Mail Security** 
Email security ensures that the message sent over the intenet are private , authentic and safe from the hacker.Two main technique used by email seurity are 
**Preety Good Privacy(PGP)**
PGP is an encryption method used to secure emails , files and digital signature .
*How PGP works:*
- Uses the public key encryption where the sender encrypt the message using the recipinet public key
- The recipinet decrypt the message using thier private key.
- Uses the digital signature to verify the sender identity.
*Fetures of PGP:*
- Confidentiality = making sure that only authorized user can read it.
- Authentication = Digital signature confirms the sender indentity
- Integrity = Ensures that the message was not changes during the transaction.

**Secure/Multipurpose Internet Mail Entension (S / MIAME)**
S/MIAME is a standard for email encryption  developed by RSA. Is is built into email services like gmail ,outlook etc
*How S/MIME works*
- Uses digital signature to verify the sender identity
- Encrypt the email using public key cryptography
- Support Attachments , and multimedia content securely
*Feature of S/MIME*
- Encryption = Protect the email content from hacker
- Digital Signature = Ensures the email is from a trusted sender.
- Integreted in Email Service provider = Work directly with major email services
## **SSL (Secure Socket Layer)**
SSL was developed by Netscape in 1990 to secure the web communication . It is used in HTTPS , online banking , emails and messaging apps.
**How SSL Works**
- *HandShaking Process* = The client(browser) and the server establish the +secure connection.
- *Encryption* = Data is Encrypted before sent over the network.
- *Authentication* = Uses the digital certificate to verify the servers identity
**Why is SSL Not used Now**
- SSL has security flaws and is no longer considered safe
- It has been replaced by TLS which is more secure

## **TLS(Transport Layer Security)**
TLS is the upgraded and secure version of SSL . It is used in HTTPS , VPNs , emails, and cloud services.
**How TLS Works**
- *TLS Handshaking* = Secure connection between the client and the server.
- *Stronger Encryption* = Uses the Advance Encryption Standard(AES) for better security.
- *Integrity Check* = Ensures that the data is not modified during the transmission.
**Versions of TLS**
- TLS 1.0 & 1.1 = old versions , not used now
- TLS 1.2 = Most widely used version today
- TLS 1.3 = Latest version , even faster and more secure

## WTLS(Wireless Transport Layer Secruity)
WTLS is a security protocol which is designed for wireless netwroks(like the mobile deices) . It is based on the TLS but optimised for lowe power desvices and slow netwroks
**WHY DO WE NEED WTLS**
- Wireless networks are more vulnarabel than Wired Netwrok.
- Traditional TLS is too heavy for the mobile devices
- WTLS provide secure communication for mobile banking , online paymenets etc
**Features of WTLS**
- Encryption = Protect the data from unatouthorized access.
- Authentication = Verifies the sender identity using the digital certificate.
- Data Integrity = Ensures that the message remains same through out the tranmission
- Optimised for wireless = Work efficiently on slow powered devices.
**How WTLS Works**
- Handshaking = The mobile device and the server establish a secure communication
- Authentication = Digital certificate verifies the identity of the server
- Encryption = Data is encrypted before sending over the network
- Integrity = Ensures that the message is not been tempered


# **UNIT = 3**
## What is Authentication Header
Authentication Header ek IPSEC protocol h jo ki ensure krta h ki jo data apko mila h wo genuine sender se h ya nahi , or transmission ke beech me kisi ne change to nahi kiya
Authentiocation Header ka main Focus hota hai:
- **Authenticaion** = Data kisne bheja h
- **Integerity** = Or Transmission ke beech me data ko kisi ne modify to nahi kiya 
Authenticatio Header data ko encrypt nahi krta , sirf verify krta hai ki data original hai ya nahi
EX = Soch le tu apne friend ko ek chitti bhejta h or use pr ek signature lga deta hai jisse friend ko pta chal jata hai ki chitti ko kisi ne beech me change nahi kiya . 
Wese hi Authentication Header ka Kaam hota hai data pr ek digital signature lga dena
### **Encapsulating Security Payload (ESP)** 
ESP bhi AH  ki trah IPSEC ka part hai . Lekin ESP zyada powerfull hai , kyuki ye data ko encrypt bhi krta hai or authenticate bhi krta hai . 
ESP main Foucs:
- **Confidentiality(Encryption)** = Data ko chupa deta hai taki koi or use na pad sake
- **Authentication** = Data kisne bheja hai
- **Integrity** = Transmission ke beech me data kisi ne modify to nahi kiya
EX = Tu apne friend ko ek chitti bhejta hai pr vo chitti tu ek box me lock krke bhejta hai jiski key sirf tere friend ke pass hai . WESE hi ESP  bhi kaam krta hai datako lock kr deta h (Encrypt)

## **Intruder**
Intruder wo log ya program hote hai jo bina kisi permission ke computer ya netwrok me hus jate hai inka maksad hota hai data churana , system bigadna , ya system ka missuse krna 
Ye exactly wese hote hai jese koi chor bina btaye ghar me ghus jaye
**Types of Intruder**
- **Masoom Intruder(bengin)** Galti se kuch galat kr deta hai , jese koi restricted file khol lena
- **Masoom Nuksaan Wala(Misfeasor)** Authorized hote hai pr jaan bho ke nuksaan phuchte hai 
- **Otusiders(Hackers)** Jinko access nahi hota pr fir bhi system me ghus jate hai
**Goal of Intruder**
- Password Churana
- System Crash krna
- Malware install krna
- Sensitive information copy krna

# **Intrusion Detection System(IDS)**
IDS ek security guard ki trah hota hai jo conitusely monotior karta hai koi unauthorized activity ya attack to nahi ho rha hai
EX= jese ghar ke bahr CCTV camera hota hai jo batata hai koi chor aa gaya - 
WESE hi IDS system ya network ko moitor krta hai or alert bhejta he agr kuch suspicius dekhe to
**How IDS Work**
- System ke sare activity jese log , files ,traffic ko monitor krta hai .
- Agr koi unusual behavius milta hai jese bhot sare failed logis to alert krta hai
- Automicatilcally action bhi leta hai jese IP ko block krdena , or admin ko alert bhejna etc
**Types of IDS**
- **Host-Based IDS** = Sirf ek system jese PC ko monitor krta hai  , Software hota hai jo log files or system changes check krta hai 
- **Network-Based IDS** = Pure netowrk ko monitor krta hai , Suspicious packets ya attack jese DDOS detect karta hai

# **Viruses** 
ye programs ya code hote hai jo computer ko nuksaan phuchate hai 
Virus khud ko copy krta hai , files ko corrupt krta hai , system ko slow krta hai , or data ko churta ahi 
**How Virus Sprread**
- Infected Pen drive , files ya emails se 
- Fake software download
- Malicius website ya ads 
**Types of computer Virus**
1. File Infector Virus
   - Program files(.exe) ko infect krta hai
   - Jab file run hot h virus bhi Chalu ho jata hai
2. Macor Virus:
   - Word,Excel jaise document me hota hai
   - Document open krte hai to activate ho jata hai
1. Boot Sector Virsu: 
   - Computer ke start hone wale part ko affect krta hai 
   - Computer start hi nahi hota ya crash ho jata hai
1. Trojan Virus:
   - Apne ap ko useful software jesa dikhata h par andr se harmful hota hai
   - data chura sakta hai
1. Worm:
   - Virus jesa hi hota hai pr apne ap network me failta hai
   - Netowrk slow ho jata hai
## **FireWall Design Principles**
Friewall ek ecurity guard ki trah hota hai jo computer netwrok ke andr or bahar jane wali traffic ko check krta hai  , Agr koi traffic ya request dangerous lagti hai to use block kr deta hai. Jaise building pe guard check krta hai ki kaun andr ja rha hai wese hi firewall data packets ko check krta hain
**Design Prinicples of Firewall**
1. **All Traffic Must go through the Firewall** = Sare data packets firewall ke thorugh hi pass hone chahiye , Bypass allowed nahi hota
2. **Only authorized traffic is allowed** = Sirf allowed trafic ko hi ag ane diya jata h baki sab block ho jata hai
3. **Firewall must be immune to attakcs** = Khud firewall ko bhi secure hona chahiye agr firewall tod diya to pura system open ho jata hai 
**Types of Firewall**
- **Packet Filetering Firewall** = Har packet ka source , destination , IP , port number check krta hai , Simple aur fast , par smart nahi hota 
- **Stateful Inspection Firewall** = Har connection ka status ya state track krta hai , Zyada secure hota hai
- **Application level Firewall** = Application jaise HTTP , FTP ka deep inspection krta hai , SLow hata hai but very secure
**Firewall kya protect krta hai**
- Unauthorized access
- Virus & malware
- DOS  attack

# unit 4
### **Cyber World**
- Cyber duniya matlab — **digital duniya**, jisme mobile, internet, laptop, computer sab aate hain.
- Jaise real life mein roads, shops, log hote hain, waise cyber world mein websites, apps, social media, email hote hain.
- Is duniya mein sab kuch **virtual** hota hai, par kaam real jaisa!
### **Cyber Crime**
Cyber crime matlab woh kaam jo online ki duniya mein **illegal ya dangerous** hote hain. Jaise:
- **Hacking:** Kisi ka password churake account mein ghus jaana 
- **Fraud:** Fake lottery/email se logon se paise nikaalna
- **Nudes Leak:** Kisi ke private photos ya videos internet pe daalna
- **Fake Profiles:** Dusre ke naam ka Facebook/Insta account banana
 Ye sab online ka **jurm (crime)** hai, aur iske liye punishment bhi hota hai!
###  **Cyber Criminals**
Cyber criminals woh log hote hain jo cyber crime karte hain.  
Types:
- **Hackers:** System crack karke data churate hain
- **Scammers:** Fake call/email se logon ko bewakoof banake paisa le lete hain
- **Dark Web Criminals:** Drugs, guns ya illegal cheeze online bechte hain
###  **Cyber Law**
- Jaise offline duniya mein police aur kanoon hota hai, waise hi **cyber world ka kanoon** bhi hota hai
- India mein cyber law ka naam hai **IT Act 2000**
  **IT Act 2000 ke under**:
- Har cyber crime ke liye proper **section** aur **punishment** fix hai
- Government aur police isi act ke base pe cyber criminals ko pakadte hain
##  **IT Act 2000**
### **1. Introduction**
IT Act 2000 India ka **pehla cyber law** tha, jo **17 October 2000** ko lagu hua.  
Iska main kaam tha:  
✔️ Digital singnature ko legal banana  
✔️ E-Governance ko boost karna  
✔️ Cyber crimes ko rokna
 **2008 mein amendment** bhi hua kyunki hackers naye tareeke dhoondh rahe the.
### **2. IT Act ke 3 Main Objectives**
#### 1. **Digital Signature Ko Legal Banana (Section 5)**
- Ab mouse ya digital pen se sign karo, woh bhi legal hai.
- **Example:** Income tax filing, bank loan documents.
#### 2. **E-Governance Ko Support Karna**
- Government ke kaam online bhi ho sakte hain — legally valid.
- **Example:** Company registration, license renewal online.
#### 3. **Cyber Crimes Ko Control Karna**
- Act ne hacking, fraud jaise crimes ke liye punishment fix kiya.
- **Example:** ATM fraud = 3 saal jail (Section 66).
### **Important Sections**

| **Section** | **Crime**                                           | **Punishment**              | **Example**                        |
| ----------- | --------------------------------------------------- | --------------------------- | ---------------------------------- |
| 43          | Bina permission ke computer ya server exploite krna | ₹1 crore tak fine           | College server hack kiya           |
| 66          | Hacking                                             | 3 saal jail + ₹5 lakh fine  | Facebook ID hack kar li            |
| 66C         | Identity Theft                                      | 3 saal jail + fine          | Fake Aadhaar banaya                |
| 67          | Obscene content upload                              | 5 saal jail + ₹10 lakh fine | MMS viral kiya                     |
| 72          | Privacy breach                                      | 2 saal jail + ₹1 lakh fine  | Hospital ne patient data leak kiya |

### **IT Act2008 Amendment**
Jaise jaise cyber crimes naye tareekon se hone lage, waise hi 2008 mein IT Act ko update kiya gaya. Is amendment se kuch **naye sections** add kiye gaye jo naye type ke cyber criminals ko rokne mein madad karte hain.
#### **Cyber Terrorism (Section 66F)**
- Desh ke system ko hack kiya, toh **life imprisonment**.
- **Example:** Bank ya power grid ko hack kiya.
#### **Child Porn Ban (Section 67B)**
- Bacchon ka obscene content = 5 saal jail + ₹10 lakh fine.
#### **Intermediary Rules**
- Facebook, WhatsApp jaise platforms ko illegal content hataana hoga.
- **Current Example:** WhatsApp se fake news hatana.
### **Famous Cases (1 Ma0rk)**
#### 1. **Sony Sambandh Case (2002)**
- IT Act ka pehla case.
- Employee ne customer data chori kiya.
###  2. **Cosmos Bank Hack (2018)**
- ₹94 crore ka scam.
- **Sections 43 + 66** use hua.
###  **Legal Recognition of Electronic Records (Section 4)**

IT Act 2000 ke **Section 4** kehte hain ki agar koi document electronic format mein hai (PDF, email, etc.), toh **wo bhi paper document jaise hi valid** hai.
**Example:** Income Tax return email se bhejna, digitally valid mana jaata hai.

### 🏛️ **Use of Digital Signatures in Government Agencies**

IT Act ke baad, **Government aur uske departments** ne digital signatures ka use karna shuru kiya for fast & paperless work.

- **Example:** Company registration, GST filings, court orders – sab mein **Digital Signatures** ka use hota hai.

---

### ✅ **Digital Signature (1 Mark)**

#### **What is a Digital Signature?**

Digital signature ek **cryptographic** technique hai jo kisi document ya transaction ki **authenticity** aur **integrity** ko verify karti hai. Matlab, **yeh confirm karta hai** ki document **genuine hai** aur **change nahi kiya gaya** hai.

#### **How Does it Work?**

1. **Private Key:** Pehli baar jab koi user digital sign karta hai, toh uske paas ek private key hoti hai. Yeh secret key hai, jo **user ke device pe** stored hoti hai.
2. **Public Key:** Iske opposite, public key hoti hai jo **server pe** stored hoti hai, jisse document ko verify kiya jata hai.
#### **Use Cases:**
- **Government documents** – Passport, tax filing
- **Banking** – Loan applications, transactions
- **Emails** – Secure email communication
    

#### **Legal Recognition (Section 5, IT Act 2000):**

IT Act 2000 ke Section 5 ke tahat, **digital signatures ko legal recognition** diya gaya hai, matlab agar kisi document pe digital signature hai, toh woh **court mein valid** hoga.


## **Network Security**
###  **1. Introduction (1 Mark)**
Network Security ka matlab hai kisi bhi network (internet, LAN, WiFi) ko **unauthorized access**, **data theft**, aur **hacking** se protect karna.
🔹 **Kyu zaroori hai?**  
Har din hazaron websites aur servers par attack hota hai.  
Real world ka tala – Network world ka firewall.
### **2. Types of Network Attacks (4 Marks)**
<u><b>Security Attacks</b></u> 
Attack on Network can be divided into two types :
*1)Passive Attacks :* 
- The attacker secreatly listens to the communication
- No changes are made to the data , so they are hard to detect
- Example :
    . EavesDropping - Listening to private conversations
    . Traffic Analysis - Studing message flow to learn useful  deatils.
*2)Active Attacks :*
- The attacker modifies or disrupts the data.
- These attack are easy to detect but causes serius harm
- Example :
    - Denial of Service(DOS) - A system is floaded with requests to make it stop working
### 🔐 **Protection Techniques**

|**Technique**|**Use**|**Example**|
|---|---|---|
|**Firewall**|Unauthorized access ko block karta hai|Windows Firewall|
|**VPN**|IP address hide karta hai|NordVPN, ProtonVPN|
|**SSL/TLS**|Data encrypt karta hai|HTTPS websites|
|**Antivirus**|Malware detect aur delete karta hai|Quick Heal, McAfee|

✅ **Best Practices:**
- Strong password (uppercase + symbols + numbers)
- Software update rakhna
- Unknown links pe click mat karna


## ✅ **1. IP Address**
### 🔷 **1. Introduction (2 Marks)**
IP Address ka full form hai **Internet Protocol Address**.  
Ye har device ko milta hai jab wo internet se connect hota hai — jaise mobile, laptop, server.  
Ye ek **unique identifier** hota hai jiske through data uss device tak pahuchta hai.
> Jaise ghar ka postal address hota hai, waise internet ka IP address hota hai.
### 🔢 **2. Types of IP Address**
#### ✅ A. **IPv4 (Internet Protocol Version 4)**
- Format: 4 numbers separated by dots (.)
- Example: `192.168.1.1`
- 32-bit address = approx. 4.3 billion addresses
#### ✅ B. **IPv6 (Internet Protocol Version 6)**
- Format: 8 groups separated by colons (:)
- Example: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
- 128-bit address = trillions of addresses
- **Future ready**: Zyda devices ke liye space
### 🧑‍💻 **3. Classes of IP Address**

| **Class** | **Range**                   | **Use**                          |
| --------- | --------------------------- | -------------------------------- |
| A         | 1.0.0.0 – 126.255.255.255   | Large networks (Companies)       |
| B         | 128.0.0.0 – 191.255.255.255 | Medium networks (Universities)   |
| C         | 192.0.0.0 – 223.255.255.255 | Small networks (Homes, Startups) |
###  **4. Static vs Dynamic IP (1.5 Marks)**

- **Static IP**: Permanent, manually assigned
  - Example: Web server, CCTV system
- **Dynamic IP**: Temporary, auto-assigned by ISP
  - Example: Home WiFi devices

## **Port Numbers**
Port numbers network security mein bahut important role play karte hain. IP batata hai ki data kis computer ko bhejna hai, aur port batata hai ki us computer ke kis application ya service ko bhejna hai.
### **Definition:**
Port number ek numerical identifier hota hai (range: 0 se 65535) jo networking mein data ko correct software service tak pahunchata hai.
### **Kaam:**
Ek device par multiple services run hoti hain, jaise web browser, email, file transfer. In sabko alag port numbers diye jaate hain jisse data sahi service tak pahunch sake.
### **Common Port Numbers:**

| Port  | Use                 |
| ----- | ------------------- |
| 20/21 | FTP (File Transfer) |
| 22    | SSH (Secure Login)  |
| 23    | Telnet              |
| 25    | SMTP (Send Mail)    |
| 53    | DNS (Domain Lookup) |
| 80    | HTTP (Web Traffic)  |
| 443   | HTTPS (Secure Web)  |

## **Socket**
**Socket** IP Address aur Port Number ka combination hota hai. Isse pata chalta hai ki data ko kahan bhejna hai aur kaunse program ko dena hai.
**Example:**
- IP Address: 192.168.1.10 (Device ka address)
- Port Number: 80 (Web browser service ke liye)
- Socket = 192.168.1.10:80
### **Socket Ka Use Kaha Hota Hai?**
1. **Client-Server Communication**  
    – Jab browser kisi website se data maangta hai
2. **Chat Apps**  
    – WhatsApp/WebSocket jaise apps real-time chat ke liye socket use karte hain
3. **Games**  
    – Online multiplayer games mein real-time data send/receive karne ke liye socket zaroori hai
### **Security Point of View:**
- Hacker agar kisi socket pe data bhejta hai bina permission ke, toh woh **unauthorized access** ban jaata hai
- Isliye firewalls check karte hain ki kis port pe kis socket connection allowed hai

## **Scanning Techniques**
Network ya system ke vulnerabilities (kamzori) dhundne ke liye scanning ki jati hai. Matlab, jaise police suspect ke ghar ke aas-paas jake check karti hai, waise hi hackers ya security experts system check karte hain.
- **Traceroute**  
    **Traceroute** bhi yeh batata hai ki internet pe tumhara data kitne servers se guzarta hai.
- **Ping Sweeping**  
    **Ping Sweeping** network mein sab devices ko ping karke check karta hai ki kaun kaun active hai.
- **Port Scanning**  
    **Port Scanning** check karta hai ki kaunse darwaze khule hain. Khula darwaza matlab waha se entry ho sakti hai, jo hacker ke liye helpful ho sakta hai.
- **ICMP Scanning**  
    Yeh ek special tarika hai devices ko ping karne ka, taaki pata chale ki device online hai ya nahi.
    



## BUFFER OVERFLOW ATTACKS

### 1. **Stack Overflow**

- Jab program ke **stack memory** me limit se zyada data daal diya jata hai, to original program ka flow bigad jata hai.
    
- Isse hacker apna code chala sakta hai.
    
- Example: `gets()` function me bada input lene par.
    

### 2. **String Overflow**

- Jab koi **string variable fixed size ka hota hai** aur hum usme bada input daal dete hain.
    
- Isse program crash ho sakta hai ya hacker ko access mil sakta hai.
    

### 3. **Heap Overflow**

- Heap memory long-running applications ke liye hoti hai.
    
- Agar attacker yahan zyada data inject kare to application ka behavior change ho jata hai.
    
- Hacker sensitive data access kar sakta hai.
    

### 4. **Integer Overflow**

- Jab number ka value limit cross kar jaye.
    
- Example: Agar ek variable 255 tak hi le sakta hai, aur hum 256 de dein, to value 0 ho jati hai.
    
- Isse logic ya security loophole aa jata hai.


## 🕵️ INTERNAL ATTACKS – **Andar se hone wale attacks**

Yeh wo attacks hote hain jo **system ke andar ya user ke aas-paas se kiye jaate hain**, bina zyada technical hacking tools ke. Yeh insaan ke behavior, dikkat ya carelessness ka fayda uthate hain.

---

### 1. **Emails (Phishing Attack)**

- Soch ek hacker tujhe ek **fake email** bhejta hai – jisme likha ho: "Your bank account needs verification. Click here!"
    
- Tu click karega, aur wo tujhe ek **fake website** pe le jaayega.
    
- Waha tu apna **username, password** dal dega.
    
- Wo hacker tera sab data chura lega.
    
- Isko **phishing** bolte hain — matlab fake email ke through login info chura lena.
    

---

### 2. **Mobile Phones**

- Kabhi-kabhi tu koi **free app ya game download** karta hai unknown site se — wo app tera data chura sakti hai.
    
- Ya koi **spam SMS aata hai** jisme link hota hai, uspe click kar diya toh phone me virus aa sakta hai.
    
- Isse hacker **photos, messages, contacts** sab access kar leta hai.
    

---

### 3. **Instant Messengers (WhatsApp, Telegram, etc.)**

- Soch koi tujhe **WhatsApp pe ek link** bhejta hai: “Dekho tumhara photo viral ho gaya!”
    
- Tu curiosity me click karega, aur tera phone hack ho sakta hai.
    
- Ya koi harmful file bhej de – jise open karte hi **malware** active ho jata hai.
    

---

### 4. **FTP Uploads**

- FTP ek server hota hai jahan log files upload/download karte hain.
    
- Agar koi hacker waha **virus ya trojan** upload kar de — aur koi usse download kar le — to wo system hack ho jata hai.
    
- FTP upload pe surveillance na ho toh **bohot bada risk** hota hai.
    

---

### 5. **Dumpster Diving**

- Soch ek company ne apna **dustbin clear kiya** — usme purane bills, login passwords, employee details ke papers the.
    
- Koi attacker wo **kachre me se nikal ke** confidential info le leta hai.
    
- Isse **financial ya identity theft** ho sakta hai.
    
- Isliye hamesha important papers ko **shredder machine** me kaat ke phenkna chahiye.
    

---

### 6. **Shoulder Surfing**

- Tu ATM pe apna PIN daal raha hai, ya phone unlock kar raha hai.
    
- Tere peeche koi banda **chupke se dekh raha hai**.
    
- Usne tera PIN dekh liya, ab wo tera account access kar sakta hai.
    
- Isse bachne ke liye **haath se screen cover karna** chahiye jab bhi password daalo.
    

## 💣 **DoS Attacks (Denial of Service Attacks)**

- Naam se hi pata chal raha hai — "Denial of Service" matlab kisi bhi service (jaise website, server, ya app) ko **band kar dena ya slow kar dena**, taki real users use **access na kar sakein**.
    
- Hacker system pe itna **load dal deta hai** ki wo **crash ya slow** ho jata hai.
    

---

### 1. **Ping of Death**

- Normal ping chhoti size ka hota hai.
    
- Lekin hacker **bahut bada ping packet** bhejta hai (limit se zyada).
    
- System us packet ko **process nahi kar pata** → aur crash ho jata hai.
    

🧠 Example: Ek aadmi ek chhoti file ko download kar sakta hai, par agar usko 10GB ki file bhej di jaaye — to system hang ho jayega.

---

### 2. **Teardrop Attack**

- Hacker **network packets** ko **tootay-phootay aur galat order** me bhejta hai.
    
- Victim ka system un packets ko **jodne ki koshish** karta hai par confuse ho jata hai.
    
- Is confusion me **system crash ho jata hai**.
    

🧠 Example: Jaise puzzle ka wrong piece galat jagah fit karne ki koshish karo — sab gaddbad ho jaata hai.

---

### 3. **SYN Flooding**

- Jab koi client server se connect karta hai, to ek 3-step handshake hota hai: **SYN → SYN-ACK → ACK**
    
- Hacker bahut saare **fake SYN requests** bhejta hai lekin kabhi **ACK nahi bhejta**.
    
- Server har request ke liye memory reserve karta hai.
    
- Memory bhar jaati hai → real users connect nahi kar paate.
    

🧠 Example: Jaise kisi restaurant me log table reserve kar lein, par kabhi aaye hi na — ab asli customer ko jagah nahi milti.

---

### 4. **Land Attack**

- Hacker ek aisi packet bhejta hai jisme **source aur destination IP address same** hota hai — victim system ka apna hi IP.
    
- System confuse ho jaata hai: "Main hi apne aap ko kyun message bhej raha hoon?"
    
- Is confusion se **system crash ya hang** ho jaata hai.
    

🧠 Example: Jaise tu apne aap ko mirror me dekh ke hi ghabra jaaye 😅

---

### 5. **Smurf Attack**

- Hacker ek **ICMP ping request** ko **broadcast address** pe bhejta hai — sab connected systems se request chali jaati hai.
    
- Sab systems ek saath reply bhejte hain victim ko.
    
- Victim system **overload ho jata hai** replies se.
    

🧠 Example: Soch tu sabko ek hi baar me message bhej de: "Reply karo!" — aur sab reply karen to phone hang ho jaata hai.

---

### 6. **UDP Flooding**

- Hacker **bahut saare UDP packets** randomly send karta hai bina kisi break ke.
    
- Victim system har packet ka reply dene ki koshish karta hai (ICMP unreachable message).
    
- CPU busy ho jaata hai → system **slow ya down** ho jaata hai.
    

🧠 Example: Jaise tu ek aadmi se baar-baar random sawal poochhe bina rukke — wo thak jaayega ya ignore kar dega.

