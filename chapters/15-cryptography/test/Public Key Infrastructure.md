

## For messages sent through an insecure channel, a properly implemented digital signature gives the receiver reason to believe the message was sent by the claimed sender. While using a digital signature, the message digest is encrypted with which key?


### Sender's private key

Receiver's public key

Sender's public key

Receiver's private key

-----------------------------------------------------------------------------------------------------------------------------

## Which of the following defines the role of a root certificate authority (CA) in a public key infrastructure (PKI)?


The root CA stores the user’s hash value for safekeeping.

### The CA is the trusted root that issues certificates.

The root CA is the recovery agent used to encrypt data when a user’s certificate is lost.

The root CA is used to encrypt e-mail messages to prevent unintended disclosure of data.

-----------------------------------------------------------------------------------------------------------------------------

## Which of the following is a characteristic of public key infrastructure (PKI)?


Public-key cryptosystems do not require a secure key distribution channel.

Public-key cryptosystems do not provide technical nonrepudiation via digital signatures.

Public-key cryptosystems are faster than symmetric-key cryptosystems.

### Public-key cryptosystems distribute public-keys within digital signatures. 

    Public-key cryptography and the public-key/private-key pair provides an important benefit: 
        the ability to widely distribute the public key on a server, or in a central directory, 
        without jeopardizing the integrity of the private key component of the key pair. 
        This eliminates the need to transmit the public key to every correspondent in the system.

-----------------------------------------------------------------------------------------------------------------------------

## A network security administrator is worried about potential man-in-the-middle attacks when users access a corporate website from their workstations. Which of the following is the best remediation against this type of attack?


Requiring strong authentication for all DNS queries

Implementing server-side PKI certificates for all connections

### Requiring client and server PKI certificates for all connections

Mandating only client-side PKI certificates for all connections


-----------------------------------------------------------------------------------------------------------------------------
## Which of the PKI components is responsible for issuing and verifying digital certificate? 


Validation authority (VA)

End user

### Certificate authority (CA)

Registration authority (RA)


-----------------------------------------------------------------------------------------------------------------------------
## A person approaches a network administrator and wants advice on how to send encrypted e-mail from home. The end user does not want to have to pay for any license fees or manage server services. Which of the following is the most secure encryption protocol that the network administrator should recommend?


IP Security (IPsec)

Multipurpose Internet Mail Extensions (MIME)

### Pretty Good Privacy (PGP)

Hyper Text Transfer Protocol with Secure Socket Layer (HTTPS)



-----------------------------------------------------------------------------------------------------------------------------
## A certificate authority (CA) generates a key pair that will be used for encryption and decryption of e-mails. The integrity of the encrypted e-mail is dependent on the security of which of the following?


Public key

Modulus length

### Private key

Email server certificate



-----------------------------------------------------------------------------------------------------------------------------


## Which of the following processes of PKI (public key infrastructure) ensures that a trust relationship exists and that a certificate is still valid for specific operations?


## Certificate validation

Certificate revocation

Certificate issuance

Certificate cryptography

        Explanation:
       
       The *certificate validation* is a process of verifying the *authenticity* of a certificate. 
       This is done by the validation authority *(VA)*.
       
       
-----------------------------------------------------------------------------------------------------------------------------

## Which of the following describes a component of public key infrastructure (PKI) where a copy of a private key is stored to provide third-party access and to facilitate recovery operations?


Key registry

Directory

## Key escrow

Recovery agent


        Key escrow : -  a key exchange arrangement 
                     - in which essential cryptographic *keys* are *stored* with a *3rd party* in escrow. 
        
        The 3rd party can: 
                    - use or allow others to *use the encryption keys* under certain predefined circumstances.
                    
-------------------------------------------------------------------------------------------------------------------

## Which element of public key infrastructure (PKI) verifies the applicant?


Verification authority

### Registration authority

Certificate authority

Validation authority


       
 
