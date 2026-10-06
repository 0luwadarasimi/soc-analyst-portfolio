# Phishing Email & SMS Investigation

**Type:** Phishing Analysis / Social Engineering  
**Source:** Google Jigsaw Phishing Quiz + structured analysis  
**Status:** Completed

---

## 1. Overview

This project documents the analysis of several realistic phishing scenarios. The focus is on identifying classic red flags that SOC analysts and end users should recognize: domain spoofing, urgency/fear tactics, mismatched sender addresses, and attempts to bypass multi-factor authentication.

---

## 2. Cases Analyzed

### Case 1 — Fake Document Share (Impersonated Coworker)

| Field          | Details                                      |
|----------------|----------------------------------------------|
| **Sender**     | Luke Johnson \<luke.json8000@gmail.com\>     |
| **Lure**       | Shared document / collaboration request      |
| **Red Flags**  | Personal Gmail address used to impersonate a colleague; link points to look-alike domain `drive--google.com` instead of the legitimate Google Drive domain |
| **Risk**       | Credential harvesting or malware delivery    |

**Recommendation:** Verify unexpected document shares via a secondary channel (Teams/Slack/phone). Hover over links before clicking.

---

### Case 2 — Fake Prize / Giveaway Scam

| Field          | Details                                      |
|----------------|----------------------------------------------|
| **Sender**     | "Coca-Cola" \<email_Gep2pQ76g78@opmajvpqjcg.georgs-faescht.com\> |
| **Lure**       | "Answer and Win" prize offer                 |
| **Red Flags**  | Completely unrelated and random sending domain; unrealistic prize claim; classic social engineering |
| **Risk**       | Credential theft, malware, or personal data harvesting |

**Recommendation:** Treat unsolicited prize notifications with extreme skepticism. Legitimate brands do not use random third-party domains for official communications.

---

### Case 3 — Fake 2FA / Verification Code Request (SMS)

| Field          | Details                                      |
|----------------|----------------------------------------------|
| **Channel**    | SMS                                          |
| **Lure**       | "Did you request a password reset?"          |
| **Red Flags**  | Urgency + false context designed to make the victim forward a real one-time code |
| **Technique**  | OTP social engineering / code interception   |
| **Risk**       | Full account takeover even when 2FA is enabled |

**Recommendation:** Never share verification codes. Legitimate services never ask you to forward a code you just received.

---

### Case 4 — Fake Google Security Alert

| Field          | Details                                      |
|----------------|----------------------------------------------|
| **Sender**     | Google \<no-reply@google.support\>           |
| **Lure**       | "Government-backed attackers" / security warning |
| **Red Flags**  | Spoofed domain (`google.support` is not an official Google domain); fear-based urgency pushing the victim to a fake login page |
| **Risk**       | Credential phishing                          |

**Recommendation:** Always check the actual domain. Official Google security emails come from `@google.com` or `@accounts.google.com`. Navigate directly to the service instead of clicking email links.

---

## 3. Key Takeaways for Analysts & Users

1. **Verify the domain** — Spoofed domains often look almost identical (extra characters, wrong TLD, etc.).
2. **Urgency and fear are red flags** — Attackers use time pressure to bypass careful thinking.
3. **Never share 2FA/OTPs** — Especially when the request was not initiated by you.
4. **Hover before you click** — Check the real destination URL.
5. **Use secondary verification** — Confirm unexpected requests through a different channel.

---

## 4. Skills Demonstrated

- Identification of phishing red flags
- Domain and sender verification
- Understanding of social engineering tactics
- Recognition of MFA bypass techniques
- Clear documentation of findings and recommendations

---

## 5. Future Improvements

- Analyze real phishing emails (headers, authentication results: SPF/DKIM/DMARC)
- Perform URL and attachment analysis with VirusTotal / Any.Run / hybrid-analysis
- Extract and document IOCs (domains, IPs, hashes)
- Map cases to MITRE ATT&CK technique **T1566 – Phishing**

---

*This analysis was performed for learning and portfolio purposes using publicly available phishing awareness material.*

