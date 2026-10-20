# Original Project Report

> Training scenario. This is a migrated copy of the original write-up; its analysis and historical references have been preserved.

Overview

🔐 Incident Report: ICMP Flood DDoS Attack

Summary  
 On March 14, 2025, the internal network of our organization experienced a two-hour disruption due to a Distributed Denial of Service (DDoS) attack. The attack involved a high-volume flood of ICMP packets that overwhelmed the network, causing all internal services to become unresponsive. Investigation revealed that the attack originated from a malicious actor exploiting an unconfigured firewall.

The incident response team mitigated the attack by:

- Blocking incoming ICMP traffic
- Shutting down non-essential services
- Restoring critical services

Subsequent analysis led to improved firewall configurations, source IP verification, deployment of traffic monitoring tools, and implementation of IDS/IPS for enhanced protection.

---

🧭 Identify

- Attack Type: ICMP Flood (DDoS)
- Vector: Exploitation of unconfigured firewall to allow unauthorized ICMP traffic
- Affected Systems: Internal network services, DNS, intranet servers

Gaps Identified:

- Lack of firewall rate-limiting on ICMP packets
- No source IP verification in place
- Absence of baseline anomaly detection

---

🛡️ Protect

- Implement firewall rules to throttle or block ICMP traffic from unknown sources
- Enable source IP verification to filter spoofed packets
- Review and update firewall configuration policies
- Conduct internal training on DDoS risks and recovery procedures
- Deploy or upgrade Intrusion Prevention Systems (IPS) and rate-limiting controls
- Enforce stricter change management for firewall settings

---

🛰️ Detect

- Deploy and configure IDS/IPS systems to flag ICMP flood patterns
- Implement network traffic monitoring to alert for unusual packet volume
- Leverage SIEM platforms like Splunk or Chronicle for correlation of traffic anomalies
- Enable real-time alerting for unauthorized protocol surges (e.g., ICMP)
- Establish traffic baselines to detect deviations

---

🚨 Respond

- Create and document an incident response playbook for DDoS and ICMP-based attacks
- Designate a response team with roles for containment, mitigation, and communication
- Maintain an incident handler’s journal for post-mortem documentation
- Implement automation scripts to trigger immediate action (e.g., traffic filtering)
- Notify affected teams, leadership, and—if applicable—law enforcement or regulatory bodies

---

♻️ Recover

- Restore disrupted services using known-good configurations
- Validate service integrity and audit logs for malicious code
- Conduct a lessons learned session and update internal SOPs
- Test business continuity and recovery processes for future resilience
- Periodically run tabletop DDoS simulations to prepare response teams

---

✅ Key Takeaways  
 This incident highlighted the importance of proactive firewall configuration, real-time traffic monitoring, and response planning. Moving forward, a layered defense strategy—including detection tools, preventative configurations, and defined recovery protocols—will ensure improved resilience against DDoS and network-layer threats.

analysis

## Scenario

![ICMP Flood DDoS Incident Response — original evidence screenshot](screenshots/evidence-01.png)

Review the scenario below.

You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services.

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack.

To address this security event, the network security team implemented:

- A new firewall rule to limit the rate of incoming ICMP packets
- Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets
- Network monitoring software to detect abnormal traffic patterns
- An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity event and integrate your analysis into a general security strategy. We have broken the analysis into different parts in the template below. You can explore them here:

- Identify security risks through regular audits of internal networks, systems, devices, and access privileges to identify potential gaps in security.
- Protect internal assets through the implementation of policies, procedures, training and tools that help mitigate cybersecurity threats.
- Detect potential security incidents and improve monitoring capabilities to increase the speed and efficiency of detections.
- Respond to contain, neutralize, and analyze security incidents; implement improvements to the security process.

Recover affected systems to normal operation and restore systems data and/or assets that have been affected by an incident.

Incident report analysis

 

|  |  |
| --- | --- |
| Summary | This morning, an intern reported to the IT department that she was unable to log in to her internal network account. Access logs indicate that her account has been actively accessing records in the customer database, even though she is locked out of that account. The intern indicated that she received an email this morning asking her to go to an external website to log in with her internal network credentials to retrieve a message. We believe this is the method used by a malicious actor to gain access to our network and customer database. A couple of other employees have noticed that several customer records are either missing or contain incorrect data. It appears that not only was customer data exposed to a malicious actor, but that some data was deleted or manipulated as well. |
| Identify | The incident management team audited the systems, devices, and access policies involved in the attack to identify the gaps in security. The team found that an intern’s login and password were obtained by a malicious attacker and used to access data from our customer database. Upon initial review, it appears that some customer data was deleted from the database. |
| Protect | The team has implemented new authentication policies to prevent future attacks: multi-factor authentication (MFA), login attempts limited to three tries, and training for all employees on how to protect login credentials. Additionally, we will implement a new protective firewall configuration and invest in an intrusion prevention system (IPS). |
| Detect | To detect new unauthorized access attacks in the future, the team will use a firewall logging tool and an intrusion detection system (IDS) to monitor all incoming traffic from the internet. |
| Respond | The team disabled the intern’s network account. We provided training to interns and employees on how to protect login credentials in the future. We informed upper management of this event and they will contact our customers by mail to inform them about the data breach. Management will also need to inform law enforcement and other organizations as required by local laws. |
| Recover | The team will recover the deleted data by restoring the database from last night’s full backup. We have informed staff that any customer information entered or changed this morning would not be recorded on the backup. So, they will need to re-enter that information into the database once it has been restored from last night’s backup. |
