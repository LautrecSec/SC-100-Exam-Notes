SC-100 Exam Notes



Resources:

John Savil’s cram video: https://www.youtube.com/watch?v=2Qu5gQjNQh4 

Zero Trust

For a deeper understanding: https://www.youtube.com/watch?v=hhS8VdGnfOU

### Microsoft Cybersecurity Reference Architecture (MCRA)
The MCRA provides a comprehensive blueprint for implementing Microsoft's security technologies. It serves as a detailed guide to help organizations plan and implement a holistic cybersecurity strategy using Microsoft's security solutions. Key aspects include:

### Microsoft Cloud Security Benchmark (MCSB)
The MCSB is a set of security best practices and recommendations specifically for securing cloud resources in Microsoft Azure. It acts as a benchmark for cloud security. Key aspects include:

Controls for logging and threat detection are controls for detecting threats on the cloud, and enabling, collecting, and storing audit logs for cloud services. These services include enabling detection, investigation, and remediation processes with controls to generate high-quality alerts with native threat detection in cloud services.


Zero Trust Rapid Modernization Plan (RaMP)
Top Priorities:  
**User access and productivity**
1. Explicitly validate trust for all access requests
- Identities
- Endpoints (devices)
- Apps
- Network

**Data, compliance, and governance**

2. Ransomware recovery readiness
3. Data

**Modernize security operations**
4. Streamline response
5. Unify visibility
6. Reduce manual effort

**As needed**
Additional initiatives based on Operational Technology (OT) or IoT usage, on-premises and cloud adoption, and security for in-house app development
** OT and Industrial IoT**:
- Discover
- Protect
- Monitor

**Datacenter & DevOps Security:**
- Security hygiene
- Reduce legacy risk
- DevOps integration
- Microsegmentation

__________________________________________


Identity

Look at MFA features for different Azure AD pricing tiers https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-mfa-licensing

FREE - security defaults only. Block legacy authentication. Password list options

P1 - All MFA available. Conditional Access

P2: Identity protection, Privileged Identity Management (PIM)


Defender for Identity - puts agents on on-prem domain controllers, ADDS, ADFS

Azure AD Connect - replicate ADDS to Az AD. This allows Identity protection to work if you allow hash of the hash syncing

Azure AD B2B - allows business partners Az AD access to your Az AD

Azure AD B2C - allows customers to use social identities to access apps


Endpoints

Mass of different devices. Computers, mobile devices, IoT.

Want the ability to register or join devices to Az AD to drive capabilities to manage.


Microsoft Endpoint Manager (MEM)

This is the combination of two products Microsoft Intune (cloud devices) and System Centre Configuration Manager (for on-prem devices and servers)
MEM allows you to pick and choose if you use Intune or SCCM to manage
MEM allows policies for compliance, can be fed back into conditional access
MEM allows : Compliance Policies, Conditional Access, Configuration profiles

Defender for Endpoint

Is for: Protecting, Detecting, Responding
Can discover endpoints that arent managed. Linux, MacOS, iOS and Android
Defender will feed data into MEM if there’s been a breach or a known attack detected
Disable USB, stop lateral movment, disable macros, signatures, cloud based ML. run threats on online sandboxes (like virustotal?)

Defender for Servers

Adaptive application hardening *uses machine learning to figure out what is normal behaviour
File Integrity Monitoring (FIM)
Defender for Servers has Adaptive Network Hardening, will give you recommendations on what you can lock down

Network

Don't trust it! No auth based on IPs
Microsegmentation
Use Network Security Groups (NSGs). These are then attached to vnets. NSGs are Layer 4
Use adaptive network hardening
Azure Firewall. Powerful, can inspect layer 7, the whole URL. can do TLS inspection by man-in-the-middling traffic
AzFirewall can integrate with Azure Front Door, which is global. TLS offload, it does WAF. Custom rules to block certain types of traffic.
Application Gateway, which is a single region will got WAF and L7 rules too
DDoS protection - standard SKU to link to vlans
Create service endpoints within a subnet, still public but more direct
Clients talking to services

Create Private endpoints over the private link service. Public IP can then be disabled, but can be accessed by S2S, Express Route or other Az vnets
Services talking to endpoints

Vnet integration . Can run within vnet, no need for Public IP
AKS. - Adds sidecar to the pods to to pod-to-pod communication, can do traffic shaping, access policies.

Infrastructure

Defender for Cloud (used to be Azure Security Centre)
There’s Defender for _______ (most services)
Cloud posture and compliance and recommendations
Can add standards for specific regulations for compliance and then get recommendations. Subscription must be enabled + enhanced.
Advanced detections can be added per service.
Can also talk to AWS and Google Cloud
Azure Policy
Guard rail for azure.  
Defender will use Azure policy for fixing/enforcing policies
On Windows, will use DSC, on Linux will use Chef
Can create a blueprint to group RG, RBAC, template and then stamp it onto a subscription
Encryption at Rest
Platform managed key (Azure manages the key for you, rotates, ect. Transparent to user)
Azure Customer Managed Key (controlled by customer)
Azure Keyvault will have support for Az Customer Managed Keys
Can use a hardware HSM
Gen2 VMs have virtual TPMs, lets you use Trusted Launch
Confidential Compute - memory and CPU are encrypted. AMD SKUs , or Intel can use Enclave

Least Privilege

RBAC
Just In-Time access
PIM (required P2) means you need to get approval for elevated permissions, and only have them for a limited time
AAD
ARM
For on-prem AD DS , you can use Privileged Access Management (PAM) . Bastion Forest, uses same SID, get a role for a certain amount of time.
Managed Identities for Az resources.  
User Assigned Identities (useful if farm of resources need same access)


Accessing VMs

Azure Bastion , is a managed jump-box service. Can be used via web portal , or with native tools. RDP or SSH.  Can integrate with JIT which will modify the NSG from the Bastion host into the VM.  This is a Defender for Server feature only

Azure ARC

Allows you to extend the Azure ARM control plane to other clouds, or to on-prem
ARC for Servers, ARC for Kubernetes, +Postgres, Hyperscale, AI
Allows you to extend Azure Defender for Cloud into other Clouds


Defender for Cloud Apps

Feeds from Az Ad, network devices and hook into SaaS
Can put in session controls to make users go via reverse proxy to go to SaaS app
It can discover what your doing
Can discover SaaS apps and give you risks and allow you to block it

DevOps

Github Advanced security feature
Depender bot
Finds vulnerabilities in code
Finds secret keys in repos
Data

Microsoft Purview
Will discover data across your environment and make you classify it
Classify with labels
Based on labels it will give you information protection
Will give you data lineage
Recommend the user classification of office data
SQL DB
Data masking
TDE
SQL Always Encrypted

Protecting against Ransomware

Azure Backup: Requires a PIN
Multi-user authorization. This is a resource guard. Someone else needs to give you a permission to do the action

SIEM/ SOAR

Security Incident Event Man / Security Orchestration Automation and Response  

This is Azure Sentinel which sits on top of a Log Analytics Workspace (LAW)
Needs Connectors
Azure
AAD
M365
SYSLOG
Custom
Detect: uses KQL
Fusion uses ML
Hunting: KQL queries you can execute to find, discover, maybe act on
Intelligence: signals for bad threats, bad IPs
Investigate: timeline view, investigation graph
trigger/event or action
Playbooks: uses logic apps

Onboarding a VM onto Microsoft Defender for Endpoint

https://www.youtube.com/watch?v=hx47uBBUi4o


Landing Zones

https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/


Microsoft Defender

https://docs.microsoft.com/en-us/azure/defender-for-cloud/defender-for-cloud-introduction

Follow interactive tutorial


Know what the Azure policy effects are: https://docs.microsoft.com/en-us/azure/governance/policy/concepts/effects#disabled






