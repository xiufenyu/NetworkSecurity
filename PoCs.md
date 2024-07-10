# Principle
The fundamental **GOAL** of reproducing PoC is to **generate network traffic**!!! Do whatever you can, to reproduce network traffic.  \
	1. Try to install the vulnerable software,  Execute the PoC                                                                    \
	2. If installing the vulnerable software or setting up the environment is too difficult,  try to **Setup a FAKE server** instead.  Then Execute the PoC. (CVE-2020-5398)       \
	3. If executing the PoC fail or too difficult:                                                              
 
	(1) Try to understand the PoC, Adjust the arguments of running PoC.  (CVE-2020-5398)        
	(2) Try to understand the PoC, **MAKE CHANGES** to the PoC code.  (CVE-2021-32648)                      
		a. Delete or comment some code   
	(3)  **Extract attack payload** from the PoC. Send it to attack the FAKE Server.                            


# Practice
CVE-2020-5398                    \
CVE-2015-8562                    \
CVE-2021-32648                   


CVE-2023-39358                   \
Authenticated SQL injection vulnerability when managing reports · Advisory · Cacti/cacti · GitHub
