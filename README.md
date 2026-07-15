\# Lab 01: Windows Incident Response \& Threat Hunting



\## 🔬 Project Overview

A controlled Red-Blue team simulation conducted to investigate reverse-shell payload execution, persistence mechanisms, and manual threat hunting techniques in a Windows 10 environment.



\## 🛠️ Infrastructure

\- \*\*Attacker\*\*: Kali Linux (msfvenom, Netcat)

\- \*\*Target\*\*: Windows 10 VM

\- \*\*Analysis Tools\*\*: Microsoft Sysinternals Process Explorer, Netstat



\## 🕵️‍♂️ Investigation Findings

1\. \*\*Initial Vector\*\*: Identified an unauthorized binary `backdoor.exe` executing within the user context.

2\. \*\*Persistence Analysis\*\*: Discovered the malicious process masquerading via a hijacked `cmd.exe` process to maintain a persistent Command-and-Control (C2) session.

3\. \*\*Neutralization\*\*: Executed a "Kill Process Tree" operation to terminate the malicious thread and all associated child processes, successfully cutting the C2 communication.



\## 📋 Full Evidence Log

| Step | Action | Evidence |

| :--- | :--- | :--- |

| 01 | Payload Generation | \[View](evidence/01\_msfvenom\_payload.png) |

| 02 | Execution | \[View](evidence/02\_backdoor\_execution.png) |

| 03 | C2 Connection | \[View](evidence/03\_c2\_established.png) |

| 04 | Process Identification | \[View](evidence/04\_malicious\_process.png) |

| 05 | Network Analysis | \[View](evidence/05\_netstat\_analysis.png) |

| 06 | Threat Neutralization | \[View](evidence/06\_neutralization.png) |

| 07 | Access Termination | \[View](evidence/07\_connection\_lost.png) |



\## 💡 Key Learnings

\- \*\*Visibility\*\*: Standard task managers lack the granular detail required for effective threat hunting; administrative privileges are essential for full system visibility.

\- \*\*Persistence\*\*: Sophisticated attackers often leverage legitimate system processes (like `cmd.exe`) to mask their footprint.

\- \*\*Neutralization\*\*: In cases of process injection, killing the parent process tree is the most effective method to ensure complete session termination.



\---

\*Simulated for educational purposes. Security Research by https://www.linkedin.com/in/rahuldavis91/\*

