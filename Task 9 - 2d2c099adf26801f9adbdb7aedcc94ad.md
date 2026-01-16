# Task 9:-

```jsx
Incident Handler’s Journal
```

```jsx
Incident Handler’s Journal
Entry 1

Date: March 14, 2025
Entry #: 1
Description (≈70 words):
This entry documents an investigation into unusual network activity detected during routine monitoring. I reviewed captured packets to determine whether the behavior suggested malicious intent. The work fits within the Detection and Analysis phase of the NIST Incident Response Lifecycle because the purpose was to validate an alert, examine network indicators, and understand the nature of the observed traffic before escalating the incident for further response.

5 W’s of the Incident

Who: The activity originated from an unidentified external IP.

What: Repeated SYN packets targeting a single port.

When: Detected at 10:15 AM during routine traffic review.

Where: A public-facing web server hosted in the DMZ.

Why: The pattern suggested an attempt to identify open ports through scanning.

Tool(s) Used

Used Wireshark to examine packet headers and flow behavior.

Filtered packets by source IP to isolate suspicious traffic.

Identified repeated SYN attempts without corresponding ACK responses.

Exported relevant packet captures for further correlation.

Entry 2

Date: March 16, 2025
Entry #: 2
Description (≈60 words):
This entry describes using Splunk to analyze authentication logs linked to potential brute-force activity. The investigation supported the Detection and Analysis phase because it focused on verifying whether repeated login failures were malicious. By reviewing event patterns, filtering logs, and correlating timestamps, I determined that the activity came from a single foreign IP performing repeated login attempts.

Tool(s) Used

Queried Splunk for failed login events across the authentication index.

Used time-based filters to identify rapid consecutive attempts.

Correlated user accounts targeted by the attempts.

Exported logs for further investigation and alert handling.

Entry 3

Date: March 18, 2025
Entry #: 3
Description (≈75 words):
This entry documents an investigation into a suspicious file hash detected on an employee workstation. The investigation occurred during the Containment, Eradication, and Recovery phase because its purpose was to assess the risk and determine if a containment action was necessary. I used external intelligence sources to validate whether the file matched known malware and gathered context about associated behaviors reported by threat feeds and malware repositories.

5 W’s of the Incident

Who: The hash was identified on a workstation used in the accounting department.

What: The file’s hash matched a known malware family.

When: Identified at 3:40 PM following an automated endpoint scan.

Where: Located in the user’s temporary downloads folder.

Why: Likely downloaded through a phishing email or misleading link.

Tool(s) Used

Queried the hash in VirusTotal for threat-intel validation.

Reviewed related malware behaviors and detection labels.

Compared results with endpoint security alerts and logs.

Documented findings for response and remediation planning.

Entry 4

Date: March 20, 2025
Entry #: 4
Description (≈70 words):
This entry focuses on reviewing Suricata alerts triggered by network signatures. My goal was to determine whether the alerts indicated real threats or false positives. The activity aligned with the Detection and Analysis phase because it involved evaluating rule triggers, analyzing supporting packet data, and confirming whether the signatures represented genuine malicious activity or routine network behavior that coincidentally matched rule patterns.

Tool(s) Used

Used Suricata to examine triggered IDS signatures and alert metadata.

Reviewed packet payloads linked to suspicious signatures.

Correlated alerts with known scanning activity and network logs.

Noted which rules required tuning or additional validation.

Reflections / Notes

Were there any specific activities that were challenging for you? Why or why not?
Some activities were more challenging than expected, especially packet analysis. It required careful attention to detail because small network indicators can easily be overlooked. Working through the steps helped build confidence, but gaining comfort with interpreting packet structures and isolating relevant data still takes practice.

Has your understanding of incident detection and response changed since taking this course?
Yes, my understanding has grown significantly. I now have a clearer sense of how incidents progress through each phase of the response lifecycle and how different tools contribute to detection, investigation, and remediation. The course provided practical examples that made the workflow more concrete and easier to apply.

Was there a specific tool or concept that you enjoyed the most? Why?
I enjoyed working with Splunk the most because it made log investigation feel structured and intuitive. The ability to search, filter, and correlate events quickly was especially useful during the investigative steps. It also helped me understand how logs reveal patterns that are not obvious at first glance
```