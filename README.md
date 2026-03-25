# 🔐 Secure Code Analysis using SAST Tools

### Comparative Study of Horusec vs Semgrep on Real-World Applications

---

## 🚀 Project Overview

This project implements a **reproducible Static Application Security Testing (SAST) framework** to evaluate vulnerabilities in real-world applications.

Two large-scale open-source systems were analyzed:

* **Anki (~151K LOC)**
* **Apache Superset (~657K LOC)**

Using:

* **Horusec**
* **Semgrep**

The goal is not just scanning — but **understanding tool behavior, detection accuracy, and real-world security impact**.

---

## 🎯 Why This Project Matters

Most SAST projects stop at running tools.

This project goes further by:

✔ Comparing detection capabilities

✔ Identifying false positives

✔ Evaluating real exploitability

✔ Highlighting supply chain risks

✔ Providing reproducible scripts

---

## 🧠 Key Contributions

* 🔍 Comparative analysis of two industry SAST tools
* ⚠️ Identification of **critical vulnerabilities (SQLi, RCE, XSS)**
* 📦 Supply chain vulnerability assessment
* 📊 Quantitative + qualitative evaluation
* 🔁 Fully reproducible scanning pipeline

---

## 🛠️ Tech Stack

| Category    | Tools                    |
| ----------- | ------------------------ |
| OS          | Kali Linux               |
| SAST        | Horusec, Semgrep         |
| Languages   | Python, TypeScript, Rust |
| Automation  | Bash                     |
| Data Output | JSON                     |

---

## ⚙️ Reproducibility 

### 1. Clone Repo

```bash
git clone https://github.com/your-username/secure-code-analysis-sast-comparison.git
cd secure-code-analysis-sast-comparison
```

### 2. Run Full Scan

```bash
chmod +x scripts/full_scan.sh
./scripts/full_scan.sh
```

---

## 🔍 Key Findings

### 🔴 Critical

* SQL Injection (Superset)
* Hardcoded credentials (Anki)
* Supply chain vulnerabilities

### 🟠 High

* Remote Code Execution (subprocess shell=True)
* Docker privilege escalation risks
* Cross-site scripting (XSS)

### 🟡 Medium

* Unsafe deserialization
* Path traversal
* Dependency vulnerabilities

### 🟢 Low

* Poor exception handling
* Assert misuse

---

## 📊 Tool Comparison

| Feature         | Horusec     | Semgrep            |
| --------------- | ----------- | ------------------ |
| Detection Depth | Medium      | High               |
| False Positives | High        | Moderate           |
| Supply Chain    | Weak        | Strong             |
| Usability       | CLI-focused | Developer-friendly |

---

## 🧠 Insight

* **Horusec → coding practice issues**
* **Semgrep → real exploitable vulnerabilities**

👉 Semgrep is more aligned with **modern AppSec workflows**

---

## ⚠️ Limitations

* Static analysis only (no runtime testing)
* Some findings in test files
* Supply chain false positives

---

## 🔮 Future Improvements

* CI/CD integration (GitHub Actions)
* Combine with DAST tools (OWASP ZAP)
* Auto-remediation suggestions
* Risk scoring model

---

## 📁 Project Structure

```
scripts/     → automated scanning
scans/       → raw outputs
results/     → processed insights
docs/        → detailed documentation
```

---

## 👨‍💻 Author

Hsu Shun Lae

MSc Cybersecurity

---
