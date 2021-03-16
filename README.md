# Reconbot
**Reconnaissance and Enumeration bot**

Reconbot allows you to speed up the process of Reconnaissance and Enumeration by automaticly running different nmap scans, enumeration scripts and brute-force scripts. All logged in their seperate files while displaying some details to be able to start poking quickly.


![pivot screenshot](https://i.ibb.co/dt19g20/image.png)


## Installation
You need 2 python packages for this script:
`sudo pip3 install termcolor bs4`

Reconbot also uses the following tools to further enumerate a target, it is recommended you install theise (most if not all are installed on kali by default):
* hydra
* gobuster
* nikto
* rpcinfo
* enum4linux
* smbmap
* snmp-check
* onesixtyone
* snmpwalk

Then you can just run reconbot:

`sudo ./reconbot 10.10.10.10`



```
usage: Reconbot [-h] [-HF] [-p] [-U] [-P] [-w] [--nmaponly] [--quick] [--bruteonly] [--verbose]

Automated Reconnaissance Bot

positional arguments:
                     Target

optional arguments:
  -h, --help         show this help message and exit
  -HF , --hostfile   File containing targets to scan
  -p , --ports       Ports to scan
  -U , --userlist    Wordlist to use for usernames when bruteforcing
  -P , --passlist    Wordlist to use for passwords when bruteforcing
  -w , --weblist     Wordlist to use for web directory bruteforcing
  --nmaponly         Only activate the nmap scripts
  --quick            Only activate quick port scanning
  --bruteonly        Only activate the hydra bruteforcing scripts
  --verbose          Display extra output in the reconbot output (things like paths gobuster finds)

EXAMPLES

reconbot 1.1.1.1                                                                        # Full recon scan of target
reconbot -HF ./hosts                                                                    # Full recon scan of targets in file
reconbot 1.1.1.1 -p 80,443                                                              # Recon scan of target only scanning port 80
reconbot 1.1.1.1 -w /usr/share/wordlist/webfiles.txt                                    # Full recon scan of target using custom web directory bruteforce wordlist
reconbot 1.1.1.1 -U /wordlist/usernames.txt -P /wordlist/passwords.txt                  # Full recon scan of target using custom username and password wordlists
reconbot 1.1.1.1 --nmaponly                                                             # Nmap only scan of target
reconbot 1.1.1.1 --nmaponly --quick                                                     # Nmap only scan of target only using quick scans
reconbot 1.1.1.1 -p 22,21 --bruteonly --quick -P /wordlist/passwords.txt                # Bruteforce only scan of target only using quick nmap scans to discover ports
```
