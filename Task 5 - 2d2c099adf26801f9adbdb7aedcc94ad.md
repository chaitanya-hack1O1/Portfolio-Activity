# Task 5:-

# **Log Evidence Review (Google Blue Team Style)**

### **Raw Log Event**

```
Event Type: Information
Event Source: AdsmEmployeeService
Event ID: 1227
Date: 10/03/2023
Time: 8:29:57 AM
User: Legal\Administrator
Computer: Up2-NoGud
IP: 152.207.255.255
Description: Payroll event added. FAUX_BANK

```

### **Key Identifying Details**

- **User involved:** Legal\Administrator
- **Device used:** Up2-NoGud
- **IP address:** 152.207.255.255
- **Action:** Unauthorized payroll modification
- **Indicators:** Use of “FAUX_BANK” suggests fraudulent banking destination

# **8. Containment & Response Actions Taken**

### **Immediate Actions**

- Stopped fraudulent transaction
- Collected event logs
- Flagged the Legal\Administrator account for review
- Confirmed finance team did not authorize changes

### **Short-Term Actions**

- Password reset of all privileged accounts
- Checked system for unauthorized remote access
- Reviewed audit logs for related activity

# **10. Conclusion:-**

The incident stemmed from poor access controls and misuse of a privileged administrative account. While the fraudulent transfer was prevented, the investigation revealed systemic weaknesses in the organization’s identity, access, and approval processes.

Implementing stronger authentication, removing unnecessary privileges, enforcing RBAC, and tightening monitoring will significantly reduce the chances of similar future incidents.