# 🧪 Methodology

## 1. Overview

This project follows a structured methodology to evaluate the effectiveness of Static Application Security Testing (SAST) tools. The approach is designed to simulate a real-world security assessment workflow applied to large-scale software systems.

The methodology consists of five key stages:

1. Application Selection
2. Environment Setup
3. Static Code Analysis Execution
4. Data Collection and Processing
5. Comparative Evaluation

---

## 2. Application Selection

Two open-source applications were selected to ensure diversity in:

* Codebase size
* Technology stack
* Real-world usage

### Selected Applications

| Application     | Description                    | LOC   | Languages          |
| --------------- | ------------------------------ | ----- | ------------------ |
| Anki            | Flashcard learning system      | ~151K | Python, Rust       |
| Apache Superset | Business Intelligence platform | ~657K | Python, TypeScript |

These applications provide:

* Heterogeneous architectures
* Multiple programming paradigms
* Realistic security exposure scenarios

---

## 3. Environment Setup

All experiments were conducted in a controlled environment to ensure consistency and reproducibility.

### Configuration

* OS: Kali Linux (Virtual Machine)
* User Privileges: Sudo-enabled non-root user
* Isolation: Dedicated VM to avoid interference

### Tool Installation

* Horusec installed via official script
* Semgrep installed using Python virtual environment

Environment consistency was maintained across all scans to eliminate variability in results.

---

## 4. Static Analysis Execution

Each application was analyzed using two SAST tools:

* Horusec
* Semgrep

### Execution Process

For each application:

1. Source code was cloned from official repositories
2. Scans were executed using default configurations
3. Results were exported in JSON format

### Commands Used

#### Horusec

```bash
horusec start -p <project_path> -o json -O output.json
```

#### Semgrep

```bash
semgrep scan --config auto <project_path> --json > output.json
```

### Rationale

* Default configurations simulate real developer usage
* JSON output ensures structured data for analysis

---

## 5. Data Collection and Processing

The output from both tools was collected and organized for analysis.

### Data Extracted

* Vulnerability type
* Severity level (Critical, High, Medium, Low)
* File location
* Code snippet (where available)

### Processing Steps

* Removal of duplicate findings
* Filtering irrelevant/test files (where identifiable)
* Categorization by severity and vulnerability type

---

## 6. Comparative Evaluation Framework

A structured comparison framework was used to evaluate the tools.

### Evaluation Criteria

#### 6.1 Detection Capability

* Number of vulnerabilities detected
* Coverage across severity levels

#### 6.2 Accuracy

* Presence of false positives
* Relevance of detected issues

#### 6.3 Security Impact

* Identification of exploitable vulnerabilities (e.g., SQL Injection, XSS)

#### 6.4 Usability

* Ease of setup and execution
* Output readability
* Developer friendliness

#### 6.5 Supply Chain Analysis

* Ability to detect vulnerabilities in dependencies

---

## 7. Validation Approach

To ensure validity:

* Results from both tools were cross-compared
* High-severity vulnerabilities were manually reviewed
* Findings were assessed based on real-world exploitability

---

## 8. Limitations of Methodology

* Static analysis only (no runtime validation)
* Default configurations may miss advanced vulnerabilities
* Some findings originate from non-production code (e.g., tests)

---
