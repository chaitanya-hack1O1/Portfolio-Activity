# Task 3:-

## **SQL Filtering Portfolio**

### **Apply Filters to SQL Queries**

### **Project Description**

This project demonstrates how SQL filtering techniques can be used to extract meaningful information from the log_in_attempts and employees tables of an organization’s database. By using conditions with AND, OR, and NOT, these queries support security monitoring, compliance review, and departmental analysis.

### **Retrieve After-Hours Failed Login Attempts**

This query returns login attempts that occurred **outside normal business hours** (before 09:00 or after 17:00) **and** were **unsuccessful**.

**`Query`**

`SELECT event_id, username, login_date, login_time, country, ip_address
FROM log_in_attempts
WHERE success = FALSE
  AND (login_time < '09:00:00' OR login_time > '17:00:00');`

### **Retrieve Login Attempts on Specific Dates**

This query retrieves all login attempts that occurred on a particular date or within a date range.

**`Query`**

`SELECT event_id, username, login_date, login_time, country, ip_address, success
FROM log_in_attempts
WHERE login_date = '2023-09-15';`

`*Example for a date range:*`

`SELECT event_id, username, login_date, login_time, country, ip_address, success
FROM log_in_attempts
WHERE login_date BETWEEN '2023-09-01' AND '2023-09-30';`

### **Retrieve Login Attempts Outside of Mexico**

This query identifies login attempts originating **from any country except Mexico**, useful for detecting unusual geographic activity.

**`Query`**

`SELECT event_id, username, login_date, login_time, country, ip_address, success
FROM log_in_attempts
WHERE country <> 'Mexico';`

### **Retrieve Employees in Marketing**

This query lists all employees assigned to the **Marketing** department.

**`Query`**

`SELECT employee_id, device_id, username, department, office
FROM employees
WHERE department = 'Marketing';`

### **Retrieve Employees in Finance or Sales**

This query displays employees who work in either **Finance** **or** **Sales**, using an OR operator to capture both conditions.

**`Query`**

`SELECT employee_id, device_id, username, department, office
FROM employees
WHERE department = 'Finance'
   OR department = 'Sales';`

`*A cleaner alternative using IN:*`

`SELECT employee_id, device_id, username, department, office
FROM employees
WHERE department IN ('Finance', 'Sales');`

### **Retrieve All Employees Not in IT**

This query filters out employees from the **IT** department, returning only those in other departments.

**`Query`**

`SELECT employee_id, device_id, username, department, office
FROM employees
WHERE department <> 'IT';`

### **Summary**

The database queries presented in this portfolio illustrate how filtering conditions in SQL can be used to investigate system activity, detect unusual login behavior, and analyze team membership across departments. By leveraging conditional operators such as AND, OR, and NOT, SQL can efficiently narrow data sets to reveal insights that support both security operations and internal organizational management.