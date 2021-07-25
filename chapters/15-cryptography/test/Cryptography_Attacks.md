### In which of the following attacks, can an attacker obtain ciphertexts encrypted under two different keys and gather plaintext and matching ciphertext?


Ciphertext-only attack

Adaptive chosen-plaintext attack

Chosen-plaintext attack

### Related-key attack

    Explanation:

    Related-key attack: 
    
      -  similar to the "chosen plaintext" attack, 
          
          except that the attacker can obtain ciphertexts encrypted under two different keys. 
    
    This is actually a very useful attack if one can obtain the plaintext and matching ciphertext. 
    
    The attack requires that the 'differing keys' 
            
                be *closely related*, 
    
    for example, in a wireless environment 
                
               where subsequent keys might be derived from previous keys. 
    
    Then, while the keys are different, they are close. 
    
    Much like the ciphertext-only attack, this one is most likely to yield a partial break.
    
--------------------------------------------------------------------------------------

### An attacker breaks an n bit key cipher into 2 n/2 number of operations in order to recover the key. Which cryptography attack is he performing?


Timing attack

Rubber hose attack

### Chosen-key attack

Known-plaintext attack


    Explanation:
      
      Chosen-key attack :

        The attacker obtains the plaintexts corresponding to an arbitrary set of ciphertexts of his own choice.
        
        Using this information, the attacker tries to recover the key used to encrypt the plaintext. 

        To perform this attack, the attacker must have access to the communication channel between the sender and the receiver.

--------------------------------------------------------------------------------------
### Out of the following attacks, which attack is a physical attack that is performed on a cryptographic device/cryptosystem to gain sensitive information?


Hash collision attack

DUHK attack

MITM attack

### Side channel attack

    Explanation:

      Side Channel Attack :

        In a side channel attack, an attacker :
            
            - monitors channels (environmental factors) 
        &   
            - tries to acquire the information useful for cryptanalysis. 
        
        
        The information collected in this process is termed as side channel information.
        
        Side channel attacks do not relate with traditional/ theoretical form of attacks like brute force attack. 
        
        The concept of the side channel attack depends on 
          
              the way systems implement cryptographic algorithms, 
         
         rather than the algorithm itself.



--------------------------------------------------------------------------------------

### Which of the following attacks mainly affects any hardware/software using an ANSI X9.31 random number generator (RNG)?


Rainbow table attack

Hash collision attack

Side channel attack

### DUHK attack 

    DUHK (don't use hard-coded keys):

        -  cryptographic vulnerability 
        
         - allows attackers to obtain encryption keys used to secure VPNs and web sessions. 
        
        -  mainly affects any *hardware/software* using 
            
                    -> an "ANSI X9.31" RNG (random number generator). 

    PRNGs algorithm  : 
    
            - The PseudoRandom Number Generators  
    
            - generate "random sequences of bits" based on the :
            
                        - *Seed *  (initial secret value) 
                      & 
                        - *current state*. 
            
            - generates "cryptographic keys" that are used to :
                    
                        *establish a secure communication channel over VPN network*.
            
       Vulnerability cause :
                
                    !!! In some cases, the *seed key* is "hardcoded" into the implementation. !!!!!
            
            Both the factors are the key issues of DUHK attack as
                    
                    any attacker could combine : 
                    
                            - ANSI X9.31
                            with 
                            - the hard coded seed key 
                     
                     to decrypt the encrypted data sent or received by that device.


--------------------------------------------------------------------------------------

### Out of the following, identify the attack that is used for cracking a cryptographic algorithm using multiple keys for encryption.


Side Channel Attack

Rainbow Table Attack

### Meet-in-the-middle Attack

DUHK Attack

    Explanation:
    
    Meet-in-the-middle attack :
        
        - best attack method for cryptographic algorithms using "multiple keys" for encryption.
       
        - reduces the number of brute force permutations needed to decode text encrypted by more than one key 
        
        - conducted mainly for forging signatures on mixed type digital signatures. 
        
        - uses "space–time tradeoff"
        
        - it is a "birthday attack" because it exploits the mathematics behind the "birthday paradox".
        
        - It is called a "meet-in-the-middle" attack because it works by :
                
                - encrypting from one end 
                & 
                - decrypting from the other end, 
             
            thus meeting “in the middle.”

        - attacker uses a "known plaintext message" :
                he has access to both  :
                
                    - the "plaintext" 
                    &
                    - respective "encrypted" text. 
    
        - takes less time than an exhaustive attack 
        
        - used by attackers for forging signatures, 
            
                -> even on "digital signatures" that use the "multiple-encryption scheme".

--------------------------------------------------------------------------------------

### Which of the following cryptography attack methods is usually performed without the use of a computer?


Ciphertext-only attack

### Rubber hose attack

Chosen key attack

Rainbow table attack

--------------------------------------------------------------------------------------

### An attacker sniffs encrypted traffic from the network and is subsequently able to decrypt it. Which cryptanalytic technique can the attacker use now in his attempt to discover the encryption key?


### Chosen ciphertext attack

Birthday attack

Meet in the middle attack

Known plaintext attack

    Explanation:
    
        - Chosen ciphertext attack: 
        
                - cryptanalysis attack

                - attacker obtains the plaintexts corresponding to an arbitrary set of ciphertexts of his own choice.

                - Using this information, the attacker tries to recover the key used to encrypt the plaintext.
    
        - Birthday attack: 
        
                - class of brute-force attacks against cryptographic hashes 

                - makes the brute forcing easier

                - depends on  Birthday paradox : 

                            - probability that 2 or more people in a group of 23 
                                   share the same birthday is

                                      -> greater than 1/2.

        - Known plaintext attack: 
            
            - cryptanalysis attack
            
            - the only information available to the attacker is 
                    
                        - some plaintext blocks 
                        
                        along with 
                        
                        - corresponding ciphertext 
                        
                        and  ????????????
                        
                        - algorithm used to encrypt and decrypt the text. 
               
               Using this information, the key used to generate ciphertext that is deduced so as to decipher other messages.

        
        - Meet-in-the-middle attack: 
        
                - best attack method for cryptographic algorithms using "multiple keys" for encryption.

                - reduces the number of brute force permutations needed to decode text encrypted by more than one key 
                
                - conducted mainly for forging signatures on mixed type digital signatures. 

                - uses "space–time tradeoff"

                - it is a "birthday attack" because it exploits the mathematics behind the "birthday paradox".

                - It is called a "meet-in-the-middle" attack because it works by :

                        - encrypting from one end 
                        & 
                        - decrypting from the other end, 

                    thus meeting “in the middle.”



--------------------------------------------------------------------------------------

### An attacker has captured a target file that is encrypted with public key cryptography. Which of the attacks below is likely to be used to crack the target file?


Memory trade-off attack

### Chosen plain-text attack 

Replay attack

Timing attack

    Explanation:
    
      - Chosen-plaintext attack: 
      
           - very effective type of cryptanalysis attack. 
           - attacker obtains the ciphertexts corresponding to a set of plaintexts of his own choosing. 
           - This can allow the attacker to attempt to derive the key used and thus decrypt other messages encrypted with that key. 
           - Basically, since the attacker knows the plaintext and the resultant ciphertext, he has a lot of insight into the key used. 
           - This technique can be difficult but is not impossible.
           - The circumstances by which an attacker may obtain ciphertexts for given plaintexts are rare. 
           - However, modern cryptography is implemented in software or hardware and is used for a diverse range of applications; 
           - for many cases, a chosen-plaintext attack is often very feasible.
           - *important* in the context of *public key cryptography*, where the encryption key is public and so attackers can encrypt any plaintext they choose.

     - Timing attack: 
            - based on "repeatedly measuring" the exact "execution times" of modular exponentiation operations. 
            - attacker tries to "break the ciphertext" by 
                    -> analyzing the time taken to execute  
                            encryption and decryption algorithm for various inputs. 
            - In a computer, the time taken to execute a logical operation may vary based on the input given. 
            - The attacker by giving varying inputs tries to extract the plaintext.
    
    - Replay attack: 
            - packets & authentication Tokens are captured using a sniffer. 
            - After the relevant info is extracted, the tokens are placed back on the network to gain access. 
            - The attacker uses this type of attack to replay bank transactions or other similar types of data transfer, 
              in the hope of replicating and/or altering activities, 
              such as banking deposits or transfers.
    
------------------------------------------------------------------------------------------------

### Which of the following cryptanalysis methods is applicable to symmetric key algorithms?


Linear cryptanalysis

Frequency Cryptanalysis

Integral cryptanalysis

### Differential cryptanalysis


    Explanation:

        Differential cryptanalysis :
        
            - form of cryptanalysis 
            
            - applicable to "symmetric key algorithms". 
            
            -  examination of differences in an input 
                    and how that affects the resultant difference in the output. 
                    
            - It originally worked only with *chosen plaintext*. 
            
            - It can also work only with "known plaintext" and "known ciphertext".

------------------------------------------------------------------------------------------------

### An attacker tries to recover the plaintext of a message without knowing the required key in advance. For this he may first try to recover the key, or may go after the message itself by trying every possible combination of characters. Which code breaking method is he using?


### Brute force

Trickery and deceit

Frequency analysis

One-time pad

---------------------------------------------------------------------------------------------


