# 🔍 Findings Summary

## 1. Overview

This section summarizes the vulnerabilities identified during the static analysis of Anki and Apache Superset using Horusec and Semgrep. The findings are categorized by severity and analyzed in terms of security impact and tool effectiveness.

---

## 2. Vulnerability Distribution

The analysis revealed vulnerabilities across all severity levels:

* 🔴 Critical
* 🟠 High
* 🟡 Medium
* 🟢 Low

Both tools identified a large number of issues; however, their **focus and detection patterns differed significantly**.

---

## 3. Critical Vulnerabilities

### Key Issues Identified

* SQL Injection (Superset)
* Hardcoded credentials (Anki)
* Vulnerable dependencies (supply chain risks)

### Analysis

Critical vulnerabilities represent the highest security risk, as they can lead to:

* Unauthorized database access
* Credential compromise
* Full system takeover

Semgrep demonstrated stronger detection of **real-world exploitable vulnerabilities**, particularly SQL injection and dependency risks.

Horusec identified fewer critical issues but flagged multiple insecure coding practices.

---

## 4. High Severity Vulnerabilities

### Key Issues Identified

* Subprocess execution with `shell=True` (Command Injection risk)
* Cross-site scripting (XSS)
* Weak cryptographic algorithms (MD5, SHA1)
* Docker misconfiguration (running as root)

### Analysis

High severity vulnerabilities are exploitable under realistic conditions and can result in:

* Remote code execution
* Data leakage
* Privilege escalation

Semgrep showed stronger detection in:

* XSS vulnerabilities
* Dependency-related issues

Horusec emphasized:

* Unsafe coding patterns
* Security misconfigurations

---

## 5. Medium Severity Vulnerabilities

### Key Issues Identified

* Unsafe deserialization (pickle)
* Path traversal vulnerabilities
* SQL queries built using string concatenation
* Outdated libraries

### Analysis

These vulnerabilities require specific conditions to exploit but still pose significant risks.

Both tools detected medium-level issues effectively, though:

* Horusec produced more alerts (higher noise)
* Semgrep produced fewer but more relevant findings

---

## 6. Low Severity Vulnerabilities

### Key Issues Identified

* Use of `assert` in production code
* Poor exception handling (`try-except-pass`)
* Minor subprocess usage issues

### Analysis

Low severity issues generally indicate poor coding practices rather than direct exploitability.

Horusec generated a large number of low-level findings, which may overwhelm developers.

Semgrep maintained a better balance between signal and noise.

---

## 7. Tool Comparison Insights

### Horusec

Strengths:

* Broad detection of insecure coding practices
* Multi-language support

Weaknesses:

* High number of false positives
* Limited prioritization of critical issues

---

### Semgrep

Strengths:

* Strong detection of exploitable vulnerabilities
* Better prioritization of high-impact issues
* Supply chain analysis capabilities

Weaknesses:

* Slightly less coverage of low-level issues

---

## 8. Key Insight

The tools differ fundamentally in focus:

* **Horusec → Code quality and security hygiene**
* **Semgrep → Real-world exploitability**

This distinction is critical when selecting a tool for:

* Development environments
* Security auditing
* DevSecOps pipelines

---

## 9. Security Implications

The findings highlight that:

* Real-world applications contain multiple exploitable vulnerabilities
* Dependency risks are a major attack vector
* Static analysis tools must be used in combination for full coverage

---

## 10. Final Conclusion

Based on the analysis:

* Semgrep is more effective for identifying **high-impact, exploitable vulnerabilities**
* Horusec is useful for improving **secure coding practices**

### Recommended Approach

A hybrid strategy combining both tools would provide:

* Comprehensive coverage
* Balanced detection
* Improved security posture

---

## 11. Future Work

* Validate findings using dynamic analysis (DAST)
* Integrate automated remediation
* Expand analysis to additional tools and applications
