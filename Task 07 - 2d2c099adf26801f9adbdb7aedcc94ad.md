# Task 07 :-

You are part of the security team at Rhetorical Hospital and arrive to work one morning. On the ground of the parking lot, you find a USB stick with the hospital's logo printed on it. There’s no one else around who might have dropped it, so you decide to pick it up out of curiosity.

You bring the USB drive back to your office where the team has virtualization software installed on a workstation. Virtualization software can be used for this very purpose because it’s one of the only ways to safely investigate an unfamiliar USB stick. The  software works by running a simulated instance of the computer on the same workstation. This simulation isn’t connected to other files or networks, so the USB drive can’t affect other systems if it happens to be infected with malicious software.

```jsx
Incident Assessment Report – Found USB Device

Summary
A USB drive bearing the hospital’s logo was found in the parking lot and examined in an isolated virtual environment to prevent potential system exposure.

Potential Contents and Risks

PII Exposure: The device could hold patient records, staff information, or contact details that qualify as personally identifiable information.

Sensitive Work Material: Internal documents, schedules, or operational data could be present and misused to target staff or disrupt workflows.

Risk to Employees and Relatives: Any names, addresses, or personal notes could be leveraged for social engineering or harassment.

Business Security Risk: Configuration files, login details, or procedural documents could offer unwanted access to hospital systems.

Personal/Work File Mixing: Storing personal files alongside work materials increases the chance of accidental disclosure and complicates security oversight.

Potential Malicious Software
The device could hide malware designed to steal information, lock systems, or enable remote access. Even high-level threats such as those that spread automatically or mimic legitimate files are possible.

Possible Consequences if Plugged In Unsecured
An uninformed employee could trigger malware that compromises their workstation, exposes patient or staff data, or disrupts hospital operations.

Information a Threat Actor Might Extract
Internal communications, identification details, operational documents, or authentication hints could all be valuable.

How Such Information Could Be Used
It may support phishing attempts, impersonation, extortion, unauthorized system access, or broader attacks against individuals or the organization.

Conclusion
The device should remain isolated, documented, and handled according to incident-response procedures. No unverified USB device should ever be connected to a standard workstation.
```

#