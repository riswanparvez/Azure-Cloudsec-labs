🛡️ Azure RBAC Privilege Management & Least Privilege Enforcement
🚀 Key Achievement
Implemented Azure Role-Based Access Control (RBAC) to manage user permissions
Demonstrated detection and remediation of excessive privileges
Enforced Principle of Least Privilege (PoLP) by reducing user permissions
📌 Overview

This project demonstrates Azure Identity and Access Management (IAM) using Role-Based Access Control (RBAC).

The goal was to simulate a real-world cloud security scenario where a user is granted elevated permissions to manage a resource, followed by a security review and remediation process to reduce privileges and enforce least privilege access.

The project also shows how Azure Activity Logs capture RBAC permission changes, providing an audit trail for security monitoring.

🎯 Objective
Implement RBAC role assignment for a user
Monitor RBAC changes using Azure Activity Logs
Identify excessive privileges
Enforce Least Privilege Access Control
🏗️ Architecture
Azure VM Resource
        │
        ▼
Azure RBAC Role Assignment
        │
        ▼
User Privilege Granted
        │
        ▼
Azure Activity Logs (Audit Trail)
        │
        ▼
Security Review
        │
        ▼
Least Privilege Enforcement
⚙️ Steps Implemented
1. Created a Test User in Azure Entra ID

A new user account was created to simulate role assignment.

Example:

testuser1

Purpose:
Simulate how organizations assign permissions to users for resource management.

2. Assigned Privileged Role Using RBAC

The user was assigned the role:

Virtual Machine Contributor

Scope:

Azure Virtual Machine Resource

This role allows the user to:

Start / Stop Virtual Machines
Restart Virtual Machines
Manage VM configurations

But does NOT allow:

IAM role changes
Network configuration changes
Storage access

Purpose:
Simulate privileged access granted to a user for operational tasks.

3. Verified RBAC Role Assignment

Azure Access Control (IAM) was used to confirm the role assignment.

Purpose:
Ensure that the user successfully received the assigned RBAC role.

4. Monitored RBAC Changes Using Azure Activity Logs

Azure Activity Logs recorded the permission change.

Example event:

Operation: Create role assignment
Status: Succeeded

Purpose:

Provide audit visibility for privilege changes, which is critical for:

Security monitoring
Compliance auditing
Incident investigations
5. Performed Privilege Review

After reviewing the assigned permissions, it was determined that the user had excessive privileges for their required access level.

Security teams commonly perform periodic IAM reviews to detect over-privileged accounts.

6. Enforced Least Privilege Access

The elevated role:

Virtual Machine Contributor

was removed and replaced with:

Reader

This restricts the user to:

Viewing resources
Monitoring resource status

Without the ability to modify or manage infrastructure.

Purpose:

Enforce the Principle of Least Privilege (PoLP) to reduce potential attack surfaces.

⚠️ Challenges Faced
Azure RBAC role selection can be complex due to the large number of built-in roles
Understanding the correct scope for role assignment
Navigating Azure IAM interfaces and permission inheritance
🧠 Key Learnings
Practical implementation of Azure RBAC
Understanding privileged vs least privilege access
Monitoring IAM changes using Azure Activity Logs
Importance of access reviews in cloud security
How excessive privileges increase security risks
🎯 Outcome
Successfully implemented RBAC role assignment
Verified audit logs for privilege changes
Identified and remediated excessive permissions
Enforced least privilege access control

This project demonstrates real-world cloud identity governance practices used by security teams.

📚 Skills Demonstrated
Azure RBAC
Identity & Access Management (IAM)
Privilege Management
Least Privilege Enforcement
Azure Activity Logs Monitoring
Cloud Security Governance
