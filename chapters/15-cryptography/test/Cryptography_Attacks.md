### In which of the following attacks, can an attacker obtain ciphertexts encrypted under two different keys and gather plaintext and matching ciphertext?


Ciphertext-only attack

Adaptive chosen-plaintext attack

Chosen-plaintext attack

#### Related-key attack

    Explanation:

    Related-key attack: 
    
      -  similar to the chosen plaintext attack, 
          
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

#### Side channel attack

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

#### DUHK attack 

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

--------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------
