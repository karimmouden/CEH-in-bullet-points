# Tunelling protocols

- Allows for the movement of data from one network to another
- Involves repackaging the traffic data into a different form, usually using encryption
  - Can hide the nature of the traffic that is run through a tunnel.

## OpenVPN

- [Open-source](https://github.com/OpenVPN/openvpn) [VPN](./../11-firewalls-ids-and-honeypots/firewall-overview.md#virtual-private-network-vpn) system
- Create secure point-to-point or site-to-site connections in routed or bridged configurations and remote access facilities
- Allows peers to authenticate each other using
  - pre-shared secret keys
  - [certificates](encrypting-communication.md#digital-certificate)
  - or username/password

## SSH (Secure Shell)

- Cryptographic network protocol for operating network services securely over an unsecured network.
- Usually used for remote command-line, login, and remote command execution.
- Replaces unsecure [Telnet](./../03-scanning-networks/banner-grabbing.md#telnet)
- Introduces **SSH file transfer (SFTP)** or **secure copy (SCP)** protocols for secure file access,transfer and management.
- **SSH handshake**
  1. [TCP three-way handshake](./../03-scanning-networks/tcpip-basics.md#three-way-handshake)
  2. Protocol/software version announcement
  3. Algorithm negotiation
  4. Key exchange using [Elliptic-curve Diffie–Hellman](encryption-algorithms.md#elliptic-curve-diffiehellman)

## IPSec

  - suite of protocols 
  - provide security services at IP layer of TCP/IP stack  =>  Network Layer in OSI model.
  - composed by 3 protocols to offer security :
  
      1. **AH** - Authentication Header Protocol.
      2. **ESP** - Encapsulation of security payload Protocol. 
      3. **IKE** - Internet Key Exchange Protocol

    1- **AH** provides  : @ **network layer** & above :

        -  authentication 
        -  integrity 
        -  anti-replay  

    2- **ESP** provides @ **Transport Layer** and above :

        - confidentiality ( Encryption)

    Hence, we can say, IPSec(AH+ESP) operates at Network Layer and provide security services at Network and above layers.

    3- **IKE** : IPSec implementations also use a **Key exchange & management** protocol ( **Internet Key Exchange** protocol)

        - required if 2 entities want to communicate securely (they sould share secret keys)
        - secure connection 
        - encrypt & decrypt messages
            - generate secret keys
            - negotiate secret keys
            - manage secret keys





- IPsec is an end-to-end security scheme
- 📝 Part of IPv4 suite so it runs on layer 3 (internet layer) in [TCP/IP model](./../03-scanning-networks/tcpip-basics.md#tcpip-model) or layer 3 (transport) in [OSI model](./../03-scanning-networks/tcpip-basics.md#osi-model)
- 📝 Provides security through
  - **Authentication** through **authenticating both parts**
  - **Integrity** through using a **hash** algorithm to ensure that data is not tampered with.
  - **Nonrepudiation** through using **public key digital signatures** to prove message origin.
  - **Confidentiality** through **encryption**

### IKE (Internet Key Exchange)

- Also known as **IKEv1** or **IKEv2** depending on the version.
- 📝 Encrypts packets (payloads and headers) between parts
- Uses [X.509](./encrypting-communication.md#x509) for public key and encryption
- Cryptographic settings are established through ***Internet Key Exchange crypto profile*** (IKE policies)
- Tool: [`ike-scan`](https://github.com/royhills/ike-scan)
  - Discover, fingerprint and test IPsec VPN servers and firewalls
  - Sends a specially crafted IKE packet to each host within a network
- 📝 Deployed widely to implement e.g.
  - virtual private networks (VPNs)
  - remote user access through dial up connection to private networks

### IPSec security architecture

- **Authentication Headers (AH)**
  - Provides connectionless integrity and authentication for the entire IP packet
  - Provides protection against replay attacks
- **Encapsulating Security Payloads (ESP)**
  - 📝 In addition to AH it provides confidentiality through encryption
  - Unlike AH, it does not provide integrity and authentication for entire IP packet
    - The outer header (including any outer IPv4 options or IPv6 extension headers) remains unprotected
  - Supports encryption-only and (❗ insecure) authentication-only configurations
- **Security Associations (SA)**
  - Provides the bundle of algorithms and data to provide the parameters necessary for AH and/or ESP

### IPSec modes of operation
    
    - Transport Mode
    - Tunnel Mode

- AH & ESP can be implemented in **both modes**

#### Transport mode

- Usually authenticated
- **Only payload** is optionally **encrypted**.
- Not compatible with NAT when authenticated.
- 📝 Used within same network

#### Tunnel mode

- **Entire packet** is **encrypted & authenticated**.
- Compatible with NAT
- 📝 Used **to create VPN** between different networks.

## PPP (Point-to-Point Protocol)

- Provides  :

    - **connection** 
    
    - **authentication**, 
    
    - **transmission encryption** and **compression**.
      
- Provides  connections over asynchronous & synchronous circuits : 

   - **router-to-router** 

or 

   - **host-to-network**
   
- Can be used to **create**  **SSH tunnels**
- operate in **OSI Layer 2** -> **Data link** 
- | Internet protocol suite layer: 1 - Link layer

### Point-to-Point Tunneling Protocol (PPTP)

- **Insecure/obselete** method for implementing virtual private networks
- Uses a TCP control channel and a Generic Routing Encapsulation tunnel to encapsulate PPP packets.
