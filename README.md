# WPA2 Handshake Security Analysis

## Overview
This project analyzes the security of a WPA2-PSK network using a captured handshake file in a controlled lab environment.

The objective was to evaluate password strength and assess offline attack feasibility.

---

## Network Architecture

`Client Device ↔ Access Point (WPA2-PSK)`

Once a 4-way handshake is captured, offline password testing becomes possible.

---

## Methodology

1. Verified handshake presence (EAPOL frames detected)
2. Used aircrack-ng to perform offline dictionary attack
3. Monitored key testing rate (~1.7M keys/sec)
4. Identified matching passphrase

---

## Why This Is a Vulnerability

WPA2-PSK allows unlimited offline password guessing once handshake is captured.

The network cannot detect these offline attempts.

---

## Risk Assessment

- Weak passwords can be cracked quickly
- Attacker does not need continued proximity
- No account lockout or rate limiting

---

## Remediation

- Upgrade to WPA3 (SAE protocol)
- Enforce high-entropy passphrases
- Implement enterprise authentication

---

## Key Takeaway

Security is only as strong as password entropy in WPA2 environments.
