# WordPress Penetration Testing Lab

## Project Overview

This project documents an authorized penetration test conducted against a simulated WordPress web server as part of the TripleTen Cybersecurity Bootcamp.

The assessment focused on identifying and exploiting vulnerabilities associated with outdated WordPress plugins and themes, evaluating the potential impact of successful exploitation, and developing remediation recommendations.

**MegaQuagga Publishing was a fictional organization, and all testing was performed within an authorized bootcamp lab environment.**

## Lab Environment and Scope

- **Target Organization:** MegaQuagga Publishing (Fictional)
- **Target Environment:** Simulated WordPress web server
- **Target Domain:** `www.megaquagga.local`
- **Assessment Type:** Web Application Penetration Testing
- **Testing Scope:** Public-facing WordPress application and associated backend services

Testing was limited to the authorized target environment. Denial-of-service attacks, excessive brute-force attempts, and destructive testing were excluded from the assessment.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Metasploit Framework | Host and service enumeration, exploitation, and post-exploitation |
| WPScan | WordPress plugin and theme enumeration and vulnerability discovery |
| Meterpreter | Post-exploitation access and interaction with the compromised system |
| Public CVE Documentation | Vulnerability research and identification of available exploits |

## Penetration Testing Methodology

### 1. Reconnaissance

- Performed ICMP connectivity testing against the target server.
- Identified blocked ICMP traffic and adjusted the lab firewall configuration to permit communication between the Red Team workstation and target server.

### 2. Vulnerability Scanning

- Used Metasploit to enumerate hosts, services, and potential vulnerabilities.
- Conducted WordPress-specific scanning using WPScan.
- Identified four outdated WordPress components associated with documented CVEs.
- Reviewed publicly available vulnerability information and exploit references.

### 3. Exploitation

- Researched publicly documented exploits associated with the identified vulnerabilities.
- Adjusted exploit parameters for the simulated target environment.
- Executed exploitation attempts against vulnerable WordPress components.
- Demonstrated unauthorized access to the target server within the lab environment.

### 4. Post-Exploitation

Following successful exploitation, the assessment documented:

- Enumeration of user accounts.
- Establishment of a reverse shell.
- Upgrading shell access to a Meterpreter session.
- Administrative-level access to the target system.
- Access to system files and directories.
- Retrieval of user credentials.
- Demonstration of the ability to modify publicly accessible web scripts.

These activities demonstrated the potential consequences of unpatched vulnerabilities within the simulated environment.

## Vulnerability Findings

Four vulnerabilities were documented during the assessment.

| Vulnerable Component | CVE | Reported CVSS | Severity |
|---|---|---|---|
| WP Advanced Search | CVE-2024-9796 | 9.8 | Critical |
| WP File Upload | CVE-2024-9047 | 9.8 | Critical |
| TwentyTwenty Theme | CVE-2024-11352 | 6.4 | Medium |
| Social Warfare | CVE-2019-9978 | 6.1 | Medium |

### Key Findings

**WP Advanced Search — CVE-2024-9796**

An outdated plugin version was identified through WPScan. The assessment documented exploitation using a publicly available exploit reference and access to high-level files and data.

**WP File Upload — CVE-2024-9047**

WPScan identified an outdated plugin version associated with a critical vulnerability. The assessment documented exploitation through adjusted URL parameters and access to files and data.

**TwentyTwenty Theme — CVE-2024-11352**

An outdated WordPress theme was identified. The report documented code injection into publicly accessible web scripts after administrative access was obtained through exploitation of CVE-2019-9978.

**Social Warfare — CVE-2019-9978**

An outdated plugin version was identified. The assessment documented creating a payload file, hosting it through a web server, and using an adjusted exploit URL to execute commands against the target environment.

## Remediation Recommendations

The penetration test report recommended the following measures:

1. **Update Vulnerable Components:** Apply current supported versions and security patches to the affected WordPress plugins and theme.
2. **Perform Regular Vulnerability Audits:** Conduct monthly reviews of installed components and investigate newly disclosed vulnerabilities.
3. **Improve Security Monitoring:** Configure SIEM behavioral analytics to help identify anomalous activity potentially associated with exploitation, reverse shells, or unauthorized access.

## Key Takeaways

This project provided practical experience with:

- Conducting reconnaissance and vulnerability enumeration.
- Using Metasploit and WPScan during an authorized penetration test.
- Researching CVEs and publicly available exploits.
- Demonstrating exploitation and post-exploitation techniques.
- Evaluating the security impact of outdated software.
- Translating technical findings into remediation recommendations and a formal penetration testing report.

The assessment reinforced the importance of software patch management, vulnerability monitoring, and defense-in-depth security practices.

## Supporting Documentation

The original penetration testing report includes the executive summary, engagement scope, methodology, detailed findings, exploitation results, and remediation recommendations.

**[View Penetration Test Report](reports/Penetration-Test-Report.pdf)**

*Note: The supporting report is the original bootcamp deliverable. Some terminology and classifications have been clarified in this README. All organizations, systems, and activities described were part of a fictional, authorized training environment.*
