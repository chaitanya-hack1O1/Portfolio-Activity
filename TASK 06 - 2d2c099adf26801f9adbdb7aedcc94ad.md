# TASK 06:-

You are a newly hired cybersecurity analyst for an e-commerce company. The company stores information on a remote database server, since many of the employees work remotely from locations all around the world. Employees of the company regularly query, or request, data from the server to find potential customers. The database has been open to the public since the company's launch three years ago. As a cybersecurity professional, you recognize that keeping the database server open to the public is a serious vulnerability.

You are tasked with completing a vulnerability assessment of the situation to communicate the potential risks to decision makers at the company. You must create a written report that explains how the vulnerable server is a risk to business operations and how it can be secured.


<img width="1212" height="887" alt="image" src="https://github.com/user-attachments/assets/1aa84115-83ab-44ce-af70-c7cabece03f9" />


# **Vulnerability Assessment Report**

**Date:** 1st January 2023

---

## **1. System Description**

The assessed system is a high-performance Linux-based database server equipped with a multi-core CPU and **128GB RAM**. It runs the latest stable Linux OS and hosts a **MySQL Database Management System**. The server communicates with internal network components over IPv4 and relies on **SSL/TLS encrypted connections** for secure transmission.

It maintains continuous interaction with other servers and supports critical business applications that depend on real-time data retrieval and storage.

---

## **2. Scope**

This vulnerability assessment focuses on evaluating the effectiveness of the **current access controls** implemented on the database server.

The review covers a 3-month window: **June 20XX to August 20XX**.

Risk analysis is aligned with **NIST SP 800-30 Rev. 1**, assessing likelihood, severity, and resulting risk.

---

## **3. Purpose**

The database server is one of the most valuable assets to the business due to the following reasons:

### **Business Value**

- It stores essential operational, customer, financial, and analytical data required for daily functions.
- Business processes such as order processing, reporting, authentication, and service availability rely on its accuracy and uptime.

### **Importance of Securing the Data**

- Exposure of sensitive data (customer information, financial records, proprietary data) can cause financial loss, legal consequences, and reputational damage.
- Unauthorized modification or corruption of the database could disrupt business workflows and compromise data integrity.
- Strong security ensures compliance with regulatory standards and maintains customer trust.

### **Business Impact if Disabled**

- Critical applications relying on the database would cease functioning.
- Operations such as transactions, customer services, analytics, and internal systems would be interrupted.
- Extended downtime may result in financial losses, SLA violations, and customer dissatisfaction.
- Business continuity would be severely impacted.

---

## **4. Risk Assessment (NIST SP 800-30 Rev. 1 Based)**

| **Threat Source** | **Threat Event** | **Likelihood** | **Severity (Impact)** | **Risk Rating** |
| --- | --- | --- | --- | --- |
| Competitor | Obtain sensitive data via exfiltration | 1 (Low likelihood) | 3 (High impact) | 3 (Moderate) |
| External Attacker | Unauthorized access through weak authentication | 2 (Moderate) | 3 (High) | 6 (High) |
| Insider Threat | Privilege misuse to alter or delete data | 2 (Moderate) | 2 (Moderate) | 4 (Medium) |
| Malware / Ransomware | Server encryption or service disruption | 1 (Low) | 3 (High) | 3 (Moderate) |
| Network Intrusion | Unauthorized IP attempting to connect to MySQL | 3 (High likelihood) | 2 (Moderate) | 6 (High) |

### **Likelihood Considerations**

- Access attempts from unknown IPs occur frequently, raising the likelihood of brute-force or scanning attempts.
- Insider misuse is moderately likely due to shared or elevated privileges.
- Targeted data exfiltration by competitors is less frequent but highly damaging.

### **Severity Considerations**

- Loss of availability would directly impact customer-facing operations and internal productivity.
- Data corruption or theft would lead to financial penalties and loss of trust.
- Business-critical services would face outages, affecting customers and revenue.

---

## **5. Approach**

The assessment examined risks related to the system’s **data storage, access mechanisms, identity controls, and network exposure**.

The probability of each threat and its potential business impact were analyzed, balancing operational requirements with confidentiality, integrity, and availability.

Findings were benchmarked against standard cybersecurity best practices and the NIST SP 800-30 Rev. 1 framework.

---

## **6. Remediation Strategy**

To address identified risks, the following security controls are recommended:

### **1. Authentication Enhancements**

- Enforce **multi-factor authentication (MFA)** for all administrative and database-level accounts.
- Implement strong password policies (complexity, rotation, lockout rules).

### **2. Authorization Controls**

- Apply the **Principle of Least Privilege (PoLP)** to restrict access strictly based on job roles.
- Use **role-based access control (RBAC)** to limit user privileges within MySQL.

### **3. Auditing and Accountability**

- Enable comprehensive **AAA (Authentication, Authorization, Accounting)** logging for all system and database activities.
- Periodically review logs for anomalies such as unauthorized query execution or privilege escalation.

### **4. Network Access Controls**

- Replace SSL with modern **TLS 1.2+ encryption** for all in-transit data.
- Implement **IP allow-listing**, restricting database connections only to corporate office IPs or approved endpoints.
- Harden the firewall to block unused ports and enforce strict inbound/outbound traffic rules.

### **5. Defense in Depth**

- Deploy layered security: network firewall → host-based firewall → database access control → encryption.
- Use file integrity monitoring and intrusion detection/prevention systems (IDS/IPS).
- Regular vulnerability scans and quarterly penetration testing.

### **6. System Hardening**

- Ensure Linux OS and MySQL software are updated regularly.
- Disable unused services and remove unnecessary packages.
- Configure SELinux/AppArmor for additional isolation.

---

## **7. Conclusion**

The database server is fundamental to business continuity and data-driven operations.

While basic security controls exist, several risks related to authentication, authorization, and network exposure require immediate attention.

Applying the recommended remediation measures—rooted in least privilege, defense-in-depth, and strong identity controls—will significantly reduce the likelihood of unauthorized access, service disruption, and data loss.
