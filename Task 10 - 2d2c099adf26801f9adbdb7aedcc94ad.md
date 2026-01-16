# Task 10:-

```
You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list. Your task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list.
```

I’m writing everything clearly, step-by-step, so you can easily understand how this algorithm works in a real SOC/health-care environment.

---

# **Project Description**

You work for a healthcare company where only certain employees are permitted to access a restricted subnetwork that contains personal patient information. Access is controlled by an **allow list** of approved IP addresses.

However, employees frequently change roles, so a **remove list** of IP addresses must also be processed regularly.

Your job is to:

1. Load the allow list.
2. Load the remove list.
3. Check whether any IP addresses in the remove list appear in the allow list.
4. Remove those IPs.
5. Save the updated allow list back to the file.

To automate this, you will build a **Python algorithm** that uses the following concepts:

- `with` statement
- `open()` function
- `.read()` method
- `.write()` method
- `.split()` method
- `for` loop
- `.remove()` method

Below is the complete code and explanation.

---

# **Python Code (Typed Version)**

```python
# File paths (example names)
allow_file = "allow_list.txt"
remove_file = "remove_list.txt"

# Step 1: Read the current allow list
with open(allow_file, "r") as file:
    allow_list = file.read().split()

# Step 2: Read the remove list
with open(remove_file, "r") as file:
    remove_list = file.read().split()

# Step 3: Loop through the remove list and remove matches
for ip in remove_list:
    if ip in allow_list:
        allow_list.remove(ip)

# Step 4: Write the updated allow list back to the file
with open(allow_file, "w") as file:
    for ip in allow_list:
        file.write(ip + "\n")

```

---

# **Explanation of Every Required Component**

## **1. `with` Statement**

You see it used here:

```python
with open(allow_file, "r") as file:

```

The `with` statement ensures:

- The file automatically opens before the block.
- The file automatically closes after the block, even if errors occur.

This prevents corruption of security-critical files.

---

## **2. `open()` Function**

Used to open a file in two modes:

- `"r"` → read mode
- `"w"` → write mode

Example:

```python
open(allow_file, "r")

```

This loads the allow list so Python can process it.

---

## **3. `.read()` Method**

Inside the `with` block:

```python
file.read()

```

This reads the **entire file as a single string**, such as:

```
"192.168.1.10\n192.168.1.11\n192.168.1.12"

```

---

## **4. `.split()` Method**

Used immediately after `.read()`:

```python
allow_list = file.read().split()

```

`.split()` breaks the string at whitespace and produces a **list**:

```python
["192.168.1.10", "192.168.1.11", "192.168.1.12"]

```

This is essential because the algorithm needs lists to compare items.

---

## **5. `for` Loop**

Used to iterate through each IP address in the remove list:

```python
for ip in remove_list:
    if ip in allow_list:
        allow_list.remove(ip)

```

The loop checks each remove candidate one-by-one.

---

## **6. `.remove()` Method**

This is the key operation:

```python
allow_list.remove(ip)

```

`.remove()` searches the list and deletes the first matching item.

Here, it deletes the IP that must be removed from the allow list.

---

## **7. `.write()` Method**

After the list is cleaned, the updated allow list is written back:

```python
file.write(ip + "\n")

```

This generates a clean, readable allow list file again.

---

# **How the Algorithm Works (Step-by-Step)**

1. Open the allow list using `open("allow_list.txt", "r")`
2. Read the file contents using `.read()`
3. Convert the contents to a list using `.split()`
4. Do the same for the remove list
5. Loop through each IP in the remove list
6. If an IP is found in the allow list, remove it using `.remove()`
7. Open the allow list file again, this time in `"w"` write mode
8. Write the updated list back using `.write()`

---

# **Final Summary**

This project demonstrates how to maintain a restricted-access IP allow list in a healthcare environment.

You built a Python algorithm that:

- Reads IPs from two files
- Splits them into lists
- Compares both lists using a `for` loop
- Removes unauthorized IP addresses
- Writes the updated allow list back safely

You learned how to properly use:

- `with` for safe file handling
- `open()` for reading/writing
- `.read()` and `.write()` for file operations
- `.split()` for converting file text into lists
- `.remove()` for modifying lists
- `for` loops for iterative checking

This type of script is essential for SOC teams that manage access controls and compliance in sensitive environments like healthcare.