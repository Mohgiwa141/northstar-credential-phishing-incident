# Northstar Services — Credential Phishing & Session Persistence Investigation

**Role:** SOC Analyst (capstone) · **Date:** 26 Oct 2026 (simulated) · **Verdict:** High Severity — Confirmed Unauthorized Access

A full investigation of a credential-phishing incident resulting in unauthorized access to a billing database. This project demonstrates evidence handling, timeline normalization (clock-skew correction), and session lifecycle analysis.

## Scenario
A spoofed helpdesk email using the lookalike domain `billing-check.example` was delivered to an employee (Maya). The attacker successfully authenticated from an external IP, creating session `S-404`. The session successfully accessed `billing-register.csv` (40,960 bytes) but was denied access to `payroll.csv`. 

**Key finding:** The attacker's session remained fully active *after* the user changed her password. It required explicit session/token revocation by administrators to finally block the attacker.

## Skills demonstrated
- **Incident Response:** NIST SP 800-61 lifecycle (scope definition, evidence preservation, escalation).
- **Log Analysis & Correlation:** Correlating endpoint logs (P01-P04), identity logs (I01-I05), network flows (N01-N03), and application audits (C01-C04).
- **Time Normalization:** Identified endpoint clock skew (120 seconds fast) and corrected timestamps to build an accurate timeline.
- **Identity & Access Management (IAM):** Analysis of OAuth tokens, session persistence, and the difference between password changes vs. session revocation.
- **Evidence Handling:** Maintaining chain of custody, documenting limitations, and identifying evidence gaps.

## Repository contents
- `report/`: The sanitized final investigation report (PDF).
- `brief/`: A link to the 3-minute executive briefing video.

## Sanitization note
All IPs are RFC 5737 documentation ranges, all domains use the reserved `.example` TLD, and all data is fictional. No real client data, credentials, or live infrastructure is included.

## Author
**Umar Mohammed**
