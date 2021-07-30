# Email footprinting

- By monitoring the email delivery and inspecting the e-mail headers
- Information includes
  - IP address of the recipient
  - Geolocation of the recipient
  - Delivery information
  - Visited links
  - Browser and OS information
  - Reading time
- Can track emails using various **email tracking tools**
  - E.g. notifies sender of the email being delivered and opened by the recipient
  - Used by marketers, sellers etc.

## Email header analysis

- Helps to determine an e-mail contains something malicious or not
- Email-headers include
  - Sender's name
  - IP/Email address of the sender
  - Mail server
  - Mail server authentication system
  - Send and delivery stamps
  - Unique number of the message

### Authentication protocol headers

- Allows you to detect forged sender addresses.
- The goal is for sender to identify itself to the receiver.
- E-mail headers include information about their pass status

#### SPF: Sender Policy Framework

- SPF :  - great technique to **add authentication to your emails**.
         - SPF is one of the authentication techniques on which DMARC is based 
         - However it has some limitations which you need to be aware of : 

                 -  SPF does not validate the “From” header. 
                      This header is shown in most clients as the actual sender of the message. 
                      SPF does not validate the “header from”, but uses the “envelope from” to determine the sending domain
                      
                 - SPF will break when an email is forwarded. 
                      At this point the ‘forwarder’ becomes the new ‘sender’ of the message and will fail the SPF checks performed by the new destination.
                  
                  - SPF lacks reporting which makes it harder to maintain 


- SPF record : 
    - DNS record that has to be added to the DNS zone of your domain. 
    
    - In this SPF record you can specify which IP addresses and/or hostnames are authorized to send email from the specific domain.
    
    - The **mail receiver** will use the **“envelope from” address** of the mail (mostly the Return-Path header) to 
            
              confirm that the sending IP address was allowed to do so. 
    
    - This will happen **before receiving the body** of the message. 
    
    - When the sending email server isn’t included in the SPF record from a specific domain the email from this server will be marked as suspicious and can be rejected by the email receiver


- E.g. `'PASS' with IP 209.85.220.69` or `'NEUTRAL' ...`
- Verifies if the domain of the e-mail owned by the sending server.
  - If not passed, many e-mail providers just block it.
- Based on e-mail servers who publish records and says "here's the IP addresses we'll send e-mails"

#### DKIM: DomainKeys Identified Mail

- **email authentication technique** 
- allows the receiver to check that an email was indeed sent and authorized by the owner of that domain. 
- done by giving the email a **digital signature**. 
- This **DKIM signature** is a **header** that is *added to the message* and is **secured with encryption**.
- DKIM signatures are **not visible to end-users**
-   =>  the validation is done on a **server level**.

- E.g. `'PASS' with domain accounts.google.com`
- Allows the receiver to verify that an email claimed to have come from a specific domain was authorized by the owner of that domain using a digital signature on the domain.

#### DMARC: Domain-based Message Authentication, Reporting and Conformance

- E.g. `PASS` or `FAIL`
- Combines 2 protocols **SPF + DKIM**
- It builds on them and adds more policy
- uses the **result of the SPF checks** and add a check on the alignment of the domains to determine its results.
- email validation system designed to protect your company’s email domain from being used for email spoofing, phishing scams and other cybercrimes. 
- DMARC leverages the existing email authentication techniques SPF (Sender Policy Framework) DKIM (Domain Keys Identified Mail). 
- DMARC **adds** an important function, **reporting**. 
- When a domain owner publishes a DMARC record into their DNS record, they will gain insight in who is sending email on behalf of their domain. 
- This information can be used to get detailed information about the email channel. 
- With this information a domain owner can get control over the email sent on his behalf. You can use DMARC to protect your domains against abuse in phishing or spoofing attacks.

## Verifying email legitimity

- Double check FROM
- Check the spelling in domain name so it's coming from the domain of the company
  - If it's random e-mail check if it's from one of the biggest domain providers or if something legit.
- Check IP of the domain
  - It can be someones computer (home router IP) or a private server
  - Major mail service providers checks to determine if domain of the e-mail is tied to the source IP of the e-mail (e.g. have a record)
    - 🤗 You can tie a public WiFi (e.g. coffee shop) IP to domain and send the e-mails from there.

## E-mail policies

- Different e-mail service provider have different policies regarding to their SMTP
- 💡 Once hacker recognizes e-mail servers then then he/she can create accounts there, send e-mails back and further to figure out what the rules are.
- E.g. google does not allow you to see the IP address of the sender
  - They proxy it behind one of their servers
  - Workarounds are not so efficient.
- Each have own ruling list
  - Determines e.g. what kind of files that can be send

## Getting an IP address from an e-mail

- You can then get IP and a lot from browser headers including
  - browser information, OS info, device types
  - Revealing your IP is not safe as even home routers have pretty static IP addresses
    - Last usually 30 days up to 3 months
    - 💡 You can still release DHCP lease in your home router settings to get a new IP from the ISP.
- You can send an image from a back-end server that you own
  - Some e-mail providers request it and hide users IP
- You can send a direct link
  - No e-mail provider can protect you from that
  - 🤗 Can be done through social engineering e.g.
    - You know from social media that Bob was celebrating yesterday. You send an e-mail stating "Hi Bob, crew and I had a great time last night, you're never going to guess what Sam did in toilet, threw himself up, check out his pictures"
  - E.g.
    1. Install apache `yum install httpd`
    2. Start apache `systemctl start httpd`
    3. Create a file: `cd /var/www/html/` then `touch <RESOURCE_NAME>;`
    4. Check logs live: `tail -f /var/log/httpd/access_log`
    5. You'll get the IP address when the link (`<IP_ADDRESS>/<RESOURCE_NAME>`) is opened
       - You can find out self IP address using `curl ifconfig.me`
    6. And you can look at the location of IP using `geoiplookup <IP_ADDRESS>;`
