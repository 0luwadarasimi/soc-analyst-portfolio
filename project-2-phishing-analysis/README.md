# Phishing Email Investigation

## Overview
This project analyzes real-world-style phishing emails using Google 
Jigsaw's phishing awareness quiz, identifying red flags that distinguish 
malicious emails from legitimate ones.

## Tools/Resources
- Jigsaw Phishing Quiz (phishingquiz.withgoogle.com)

## Findings

### 1. Fake Document Share (Impersonated Coworker)
**Sender:** Luke Johnson <luke.json8000@gmail.com>
**Red Flag:** Personal Gmail address impersonating a colleague, containing 
a link to a look-alike domain (`drive--google.com`) instead of the real 
Google Drive domain.

### 2. Fake Prize/Giveaway Scam
**Sender:** "Coca-Cola" <email_Gep2pQ76g78@opmajvpqjcg.georgs-faescht.com>
**Red Flag:** Random, mismatched sending domain unrelated to Coca-Cola, 
combined with an unrealistic "Answer and Win" prize offer — a classic 
social engineering lure.

### 3. Fake 2FA/Verification Code Request
**Channel:** SMS
**Red Flag:** Attacker used urgency and false context ("did you request 
a password reset?") to trick the target into forwarding a real one-time 
verification code — a technique that bypasses 2FA entirely.

### 4. Fake Google Security Alert
**Sender:** Google <no-reply@google.support>
**Red Flag:** Spoofed sender domain (`google.support` is not an official 
Google domain), paired with fear-based urgency ("government-backed 
attackers") to drive the victim toward a fake login page.

## Key Takeaways
- Always verify sender domains carefully — spoofed domains often look 
  nearly identical to the real one.
- Urgency and fear are common phishing tactics used to bypass careful 
  thinking.
- Never share 2FA/verification codes outside of a process you personally 
  initiated.
- Hover over links before clicking to check the actual destination URL.

