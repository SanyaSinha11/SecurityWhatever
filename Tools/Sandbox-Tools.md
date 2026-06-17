1. Sandbox testing for WIZ and OLIGO, end-to-end automation

# **Sandbox Testing**

### What is Sandbox?

A **sandbox** is a **safe, isolated environment** where you can run, test, or experiment with something without affecting the real system.

The sandbox is the **environment/infrastructure**, not necessarily a standalone application. It can be pre-built (Docker, VMs, cloud sandboxes) or a custom platform that your team develops on top of those technologies

It is primarily a concept. That environment can be created in many ways:
- A Virtual Machine (VM)
- A Docker container
- A Kubernetes namespace
- A dedicated cloud environment
- A browser process
- A custom-built application

So a sandbox is **not a specific software product**, although there are products that provide sandbox functionality.

Sandbox testing means:
	Performing tests inside a sandbox environment instead of on the real system.

### Requirements

- WIZ
- Oligo
- JIRA

### Tools 

1. **DefectDojo** - 
   Centralizing security findings from multiple scanners
		- 100+ parser integrations (WIZ, OWASP ZAP, Trivy, Semgrep, etc.)
		- Built-in JIRA bidirectional sync
		- Deduplication and risk scoring
		- REST API for automation
		- Mature, widely adopted in DevSecOps pipelines
		- Product -> Engagement -> Test -> Finding hierarchy matches workflow
		- No native Oligo parser
		- Doesn't orchestrate sandbox testing itself
		- Limited AI/Agent capabilities
   
2. **OpenSOAR -** 
   SOAR stands for Security Orchestration, Automation, and Response.
   Alert-to-response automation with Python-native workflows
		- Python-native playbooks
		- Async/await for parallel execution
		- Apache 2.0 license, self-hosted
		- AI-ready architecture
		- Real-time alert ingestion
		- Fewer integration than commercial tools
		- Need to build custom integrations for WIZ/Oligo/JIRA

3. **Allama -**
		- 80+ integrations (SIEM, EDR, JIRA, Slack, AWS, etc.)
		- Visual workflow builder + AI agents
		- Multi-tenant, enterprise-ready
		- Self-hosted, zero vendor lock-in
		- May not have native WIZ/Oligo connectors out of the box
		- Requires infrastructure setup
   
4. **AI Agent Framework (Agentic Approach) -**
		- PwnKit (0sec-labs)
		- Zen-AI-Pentest
		- OpenAnt (Knostic)


---
---
