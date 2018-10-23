---
date: "2018-01-01T15:00:00-05:00"
title: "Title"
authors: []
categories:
 - 
tags:
 - 
draft: true
---

- - PAM is not enough to stop credential theft because when you're using a jump server, your managed credentials are still exposed to any remote server you're connecting to

  - Credentials are exposed in the memory of the target server (LSASS Process)

  - Secured no-cost alternative to Jump Servers with suitable hardware and Windows 10

  - - If you’re using a jump server just for RDP – you can get the same security using built-in features.

    - - Credential Guard, Virtual Secure Mode (VSM) 
      - RDP Restricted Admin Mode
      - RDP Remote Credential Guard

  - Summary of bypass techniques

  - - Foothold in the target server

    - - Credentials fully exposed when using Jump Server

      - - TGT Ticket validation isn’t associated with password rotation
        - Hashes, Passwords are still valid until password rotation

      - Token Manipulation Technique – Process Token Stealing

      - RDP Terminal Session Hijacking

      - Scraping Service Account’s credentials from the registry

    - Foothold only in the source endpoint

    - - Keyloggers to capture PAM login credentials if 2FA isn’t activated
      - Capture Clipboard when PAM is copying credentials from the vault to the RDP parameters
      - RDP Terminal Session Hijacking

    - Foothold anywhere

    - - Use vulnerability in the vault server, vault operating system, or installed service to expose sensitive vault information
      - Hunt for PAM / PIM / Vault / Jumpserver admins
      - Kerberoasting Unsupported Service Account’s credentials
      - Kerberoasting Managed Service Account’s credentials if not set to at least 11 characters

  - Details

  - - <https://jblog.javelin-networks.com/blog/can-jump-servers-and-privileged-account-management-really-stop-credentials-theft/> 

    - Mgt server is changing and rotating the password of a managed account, but once you're authenticated using Kerberos, you receive a TGT ticket from the Domain Controller. This TGT ticket indicates an already authenticated token that doesn’t need to be revalidated. The TGT ticket has a life of its own and it's configured by the GPO policy not your mgt server, and default is 10 hours. SO if the mgt solution closes the session you can still take that TGT ticket and use it

    - Automatic service account password change feature still leaves vulnerability to Kerberoasting. 

    - - Service accounts are associated with a TGS ticket, and it can be requested by anyone in the domain. These tickets are encrypted with the NTLM hash password. You can crack this ticket locally and isolate the valid NTLM hash, and do so without being detected
      - If the service account password is unmanaged, it will be easier to crack. If it's managed, you can make it longer and use a more complicated charset. The majority of PAM solutions don't enforce a password length, so even if the account is managed it can still be vulnerable. Need to evaluate how long and complex the service account passwords are, and also how often they're rotated, and evaluate if you're secure or not

    - Keylogging

    - - If the endpoint user is infected, and you log the credentials to the vault. Or steal the contents of the clipboard after the management tool checks the password out to you

    - Process token stealing/manipulation

    - - Can't be mitigated by jumpservers & PAM. Even if (1) PIM and jump servers are fully deployed, and all domain accounts, service accounts, applications, and services are managed (2) all domain admins are using the jump server to interact with your remote endpoints and services (3) you have a red forest domain design (4) you're using a protected users group for powerful accounts (5) kerberos ticket validation policies are set to minimal exsposure…you're still open for these kinds of attacks
      - Attackers can hijack live sessions of admins with token manipulation or RDP session hijacking. Both implemented in mimikatz tool using the command token::elevate /domainadmin
      - If there is anyone connected to the target computer you are at, you can hijack their token and eventually compromise their credentials

    - RDP / Terminal Services (TS) Session Hijacking

    - - Anyone with local high privileges can control and connect to any other remote sessions if you are on the same machines. Normally to switch between sessions on the same server you have to re-enter your credentials again. With this technique, you can elevate your local privileges to System by using an exploit or mimikatz, and then you can connect to any live RDP session running on the same computer or server without having to reenter any credentials. So your jumpserver is vulnerable after you check out the creds

    - RCE to the vault

    - - It's unflattering to talk about as solution implementers, but the PIM/PAM tools can be vulnerable themselves. You have this new crown jewel and new attack vector. What happens when that tool isn't implemented securely?

      - This is becoming a reality. There have been recent vulnerabilities, one of them exposes leading enterprise vault vendor server memory (and possibly, the sensitive information stored there)

      - CVE-2018-9842, CVE-2018-9843

      - One vulnerability can now expose all of the domain's secrets, expose all credentials of vault users/managers, and result in complete compromise of the domain with the first exposed user

      - - RCE to the vault --> Expose one domain admin --> DC-Sync to gather the KRBTGT account's hash --> Golden Ticket

      - Could also be a vulnerability on the server that hosts the vault which leads to a similar issue