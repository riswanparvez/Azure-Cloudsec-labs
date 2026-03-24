
# 🛡️ Azure Security Posture Improvement using Microsoft Defender for Cloud

## 📌 Overview
This project focuses on improving the Azure Secure Score by implementing security recommendations provided by Microsoft Defender for Cloud. The goal was to simulate real-world cloud hardening and security posture management.

## 🎯 Objective
Improve Secure Score from ~0 to a higher value by remediating critical security recommendations.

## 🏗️ Architecture

Azure Resources → Defender for Cloud → Recommendations → Secure Score Improvement

## ⚙️ Steps Implemented

### 1. Accessed Microsoft Defender for Cloud
- Navigated to Secure Score dashboard

**Purpose:**
Identify current security posture and recommendations

### 2. Analyzed Security Recommendations
- Reviewed high-impact recommendations

**Purpose:**
Prioritize actions that provide maximum security improvement

### 3. Remediated Recommendations
- Used “Fix” option for automated remediation

**Purpose:**
Quickly apply security configurations

### 4. Installed Guest Configuration Extension
- Enabled in-guest policy enforcement

**Purpose:**
Ensure compliance and monitor configurations inside VM

### 5. Implemented Security Controls
- Enabled monitoring
- Applied configurations
- Reviewed policies

**Purpose:**
Reduce attack surface and improve visibility

## ⚠️ Challenges Faced
- Azure UI complexity  
- Understanding which recommendations to prioritize  
- Delay in Secure Score updates  

## 🧠 Key Learnings
- Cloud security posture management  
- Risk prioritization  
- Defender for Cloud capabilities  
- Practical security implementation  

## 🎯 Outcome
- Improved Secure Score  
- Strengthened VM security posture  
- Gained hands-on experience with real-world security controls  

## 📚 Skills Demonstrated
- Azure Security  
- Microsoft Defender for Cloud  
- Secure Score optimization  
- Risk mitigation  
- Cloud hardening  
## 📸 Screenshots

### 🔴 Secure Score Before Remediation
This shows the initial insecure state of the environment before applying any security controls.
![Secure Score Before](images/secure-score-before.png)

### 🛠️ Security Hardening – Just-In-Time (JIT) VM Access
Restricted RDP (port 3389) access using JIT to minimize exposure to the internet.
![JIT Access](images/jit-access.png)

### 🔐 Network Security Group (NSG) Configuration
Configured inbound rules to control traffic and reduce attack surface.
![NSG Rules](images/nsg-rules.png)

### 🟢 Secure Score After Remediation
Security posture improved after applying recommendations and hardening configurations.
![Secure Score After](images/secure-score-after.png)
