# Task 4:-

You’re the first cybersecurity professional hired by a growing business.

Recently, a deposit was made from the business to an unknown bank account. The finance manager says they didn’t make a mistake. Fortunately, they were able to stop the payment. The owner has asked you to investigate what happened to prevent any future incidents.

To do this, you’ll need to do some accounting on the incident to better understand what happened. First, you will review the access log of the incident. Next, you will take notes that can help you identify a possible threat actor. Then, you will spot issues with the access controls that were exploited by the user. Finally, you will recommend mitigations that can improve the business' access controls and reduce the likelihood that this incident reoccurs.

# **🛡️ Incident Review: Unauthorized Bank Transfer Attempt**

## **1. What Happened (Incident Summary)**

A deposit was initiated to an **unknown bank account** from inside the business’s system.

The **finance manager denies initiating it**, and the transfer was luckily **stopped in time**.

You were asked to investigate the logs and determine how this unauthorized activity occurred.

This type of incident is typically classified as **Unauthorized Account Access** or **Privilege Misuse**.

---

# **2. Access Log Review (What the logs usually show)**

When reviewing access logs in incidents like this, you typically look for:

### **✔️ Suspicious login patterns**

- Logins at unusual hours
- Logins from foreign IP addresses or unknown devices
- Multiple failed logins before a successful one
- Logins from locations different from the finance manager’s typical pattern

### **✔️ Activity timeline**

You would check:

- When the account was accessed
- What actions were performed
- The exact timestamp of the transfer initiation

### **✔️ Permissions used**

Was the user performing the action actually **authorized** to make deposits?

### **✔️ System fields changed**

Sometimes, attackers modify bank account fields or vendor details to redirect payments.

**Example insight:**

You might find that the attacker logged in using the finance manager’s credentials.

---

# **3. Notes About the Possible Threat Actor**

Based on incidents like this, the threat actor may fall into these categories:

### **A. External attacker using stolen credentials**

Most likely scenario.

How credentials get stolen:

- Phishing email (“Please update your password”)
- Keylogger on system
- Password reused on another hacked website
- MFA not enabled

### **B. Insider threat**

Someone inside the company who:

- Has access to financial tools
- Intentionally changed bank details
- Tried to redirect funds

### **C. Compromised device**

If the finance manager’s computer is infected, the attacker could operate remotely.

Your notes would reflect:

- Login origin
- User agent (device/browser info)
- Any policy violations
- Any suspicious prior behavior

---

# **4. Access Control Issues Identified (Weaknesses that were exploited)**

These are the most common issues that lead to this exact type of incident:

### **1. Weak or reused passwords**

If one credential is compromised, attacker gains access.

### **2. No Multi-Factor Authentication (MFA)**

Without MFA, one password is all that’s needed.

### **3. Over-permissioned accounts**

Finance account might have had unnecessary privileges.

### **4. No transaction approval workflow**

If one user alone can change account details or initiate transfers, it’s a risk.

### **5. Poor audit log monitoring**

No real-time alerts for suspicious financial activity.

### **6. Lack of segregation of duties**

Same person can create vendors, edit bank details, and send payments — dangerous.

---

# **5. Recommended Mitigations (How to stop this from happening again)**

These are the standard, effective security improvements:

---

## **🔐 A. Improve Access Controls**

### **1. Enforce MFA on all critical systems**

This alone stops 99% of credential-based attacks.

### **2. Strengthen password policy**

- Minimum 12–14 characters
- Block reused passwords
- Periodic forced resets not required, but early reset after incident is essential

### **3. Implement least privilege access**

Ensure finance users only have permissions needed for their role.

---

## **🧾 B. Improve Financial Controls**

### **1. Dual control approval**

Two people must approve:

- Vendor bank changes
- Payments
- Fund transfers

### **2. Transaction alerts**

Instant SMS/email alerts for any financial activity.

---

## **🖥️ C. System Security Improvements**

### **1. Enable geo-based login alerts**

Flag logins from unusual IPs instantly.

### **2. Device hardening**

- Update OS and applications
- Enable antivirus and endpoint monitoring
- Check for malware/keyloggers

---

## **🧑‍🏫 D. Employee Awareness Training**

Train staff to detect:

- Phishing emails
- Fake password reset pages
- Suspicious attachments

---

## **🗂️ E. Log Management + Monitoring**

Implement:

- SIEM for alerting
- Daily log review
- Anomaly detection

---

# **6. Final Explanation (Clear Summary)**

The incident was caused by someone gaining unauthorized access to a finance-related account and initiating a transfer to an unknown bank account. The root cause is likely **compromised credentials**, **weak access controls**, or **missing approval workflows**.

With the recommended mitigations—especially MFA, least privilege, transaction approval, monitoring, and employee training—the business can significantly reduce the risk of similar incidents in the future.