# Nafath Discovery Mission (NAFATH-V4) - Executive Brief

Version: NAFATH-V4
Track: Networking

## Overview
Securing the software supply chain requires a defense-in-depth approach spanning software design, artificial intelligence models, mobile interfaces, core network routing, cybersecurity response mechanisms, and data governance. A national service provider must ensure that components across all six IT domains remain protected from unauthorized tampering, credential exposure, and malicious routing interferences. By integrating zero-trust architecture, standardized verification protocols, cryptographic route validation, and comprehensive Software Bills of Materials (SBOMs), organizations can establish a resilient digital infrastructure capable of mitigating complex modern cyber threats across every stage of service deployment.

## Software
According to the Twelve-Factor App methodology, configuration and secrets must be stored in environment variables rather than hardcoded into the application codebase. Hardcoding credentials risks leaking sensitive keys through version control systems like GitHub. Environment variables provide a strict separation between code and configuration, allowing smooth deployments across development, staging, and production environments without recompiling source code or modifying codebase files.

Resource: The Twelve-Factor App: Config - https://12factor.net/config

## AI
Adversarial attacks on machine learning systems are broadly categorized into data poisoning and evasion attacks. Poisoning occurs during the training phase, where malicious data is injected to manipulate model behavior. Evasion attacks occur during the inference phase, where attackers craft adversarial inputs to trick a trained model into false predictions without altering training parameters.

Resource: NIST SP 800-218: Secure Software Development Framework - https://csrc.nist.gov/publications/detail/sp/800-218/final

## Mobile
The OWASP Mobile Application Security Verification Standard (MASVS) is a framework that defines security requirements for mobile applications. It establishes standardized security levels (MASVS-L1 and MASVS-L2) alongside reverse-engineering resiliency requirements (MASVS-R). Developers use MASVS as a baseline to conduct threat modeling, verify secure storage, validate network communications, and prevent client-side vulnerabilities.

Resource: OWASP Mobile Application Security Verification Standard - https://mas.owasp.org/MASVS/

## Networking
BGP route hijacking occurs when a malicious Autonomous System advertises unauthorized IP prefixes, causing internet routers to misroute traffic to malicious destinations. Resource Public Key Infrastructure (RPKI) uses Route Origin Authorizations (ROAs) to cryptographically verify if an AS is authorized to announce specific prefixes. However, RPKI does not protect against path manipulation within valid AS routes.

Resource: RFC 6480: An Infrastructure to Support Secure Internet Routing - https://www.rfc-editor.org/rfc/rfc6480

## Cybersecurity
The Log4Shell vulnerability (CVE-2021-44228) in Apache Log4j allowed unauthenticated Remote Code Execution (RCE) via arbitrary JNDI lookups. Rated 10.0 on the CVSS scale due to its widespread usage and trivial exploitation, it was mitigated by disabling JNDI lookups and updating Log4j to version 2.17.0 or higher.

Resource: CISA Alert: Vulnerability in Apache Log4j - https://www.cisa.gov/uscert/ncas/alerts/aa21-351a

## Data
A Software Bill of Materials (SBOM) is a formal, nested inventory detailing software components and supply chain relationships. Minimum data fields required include Supplier Name, Component Name, Version of Component, Other Unique Identifiers, Dependency Relationship, Author of SBOM Data, and Timestamp.

Resource: CISA Software Bill of Materials (SBOM) - https://www.cisa.gov/sbom

## Misconception in My Track
A common misconception in networking is that enabling RPKI with BGP Origin Validation completely solves BGP hijacking. While RPKI cryptographically verifies whether an Autonomous System is authorized to originate a specific prefix, it does not validate the path traversed between Autonomous Systems. Attackers can still execute path-spoofing attacks by appending authorized AS numbers to malicious BGP updates. Section 3 of RFC 6480 confirms that RPKI ROAs only validate origin AS authorization and do not guarantee path integrity.
## Open Question
How will future Autonomous System Provider Authorization (ASPA) mechanisms integrate into existing edge router hardware without introducing severe processing latencies during dynamic BGP route convergence?



