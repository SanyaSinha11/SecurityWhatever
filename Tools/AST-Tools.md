1. Find publicly exposed endpoints and flag them for authorization/authentication.

# **API Security Testing Tool**

### Findings

Existing tools that provide similar functionalities:
- Nuclei -> token spray template
- Feroxbuster
- FFuF (Fuzz Faster U Fool)
- Kiterunner -> custom wordlist

This could be performed in two ways - 
based on source code
	(SAST)
		Semgrep
		TruffleHog
		Bearer
based on application
	(DAST)
		OWASP ZAP (ZAP HUD)
		Burp Suite
		Truffle Hog Chrome Extension

### Stages

1. Discover Endpoints
2. Check Exposure and Auth Test
3. Data Leakage Detection
4. Risk Scoring
5. Report Generation


---
---
