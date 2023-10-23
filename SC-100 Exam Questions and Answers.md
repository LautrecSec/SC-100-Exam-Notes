## SC-100 Exam Questions and Answers

Question 1
You have an Azure subscription.

Your company has a governance requirement that resources must be created in the West Europe or North Europe Azure regions.

What should you recommend using to enforce the governance requirement?

A. Azure management groups
B. custom Azure roles
C. Azure Policy assignments
D. regulatory compliance standards in Microsoft Defender for Cloud

Answer : C

Question 2
You have Microsoft Defender for Cloud assigned to Azure management groups.
You have a Microsoft Sentinel deployment.
During the triage of alerts, you require additional information about the security events, including suggestions for remediation.
Which two components can you use to achieve the goal? Each correct answer presents a complete solution.
NOTE: Each correct selection is worth one point.
A. Microsoft Sentinel threat intelligence workbooks
B. Microsoft Sentinel notebooks
C. threat intelligence reports in Defender for Cloud
D. workload protections in Defender for Cloud


Answer : AC

A: Workbooks provide insights about your threat intelligence
Workbooks provide powerful interactive dashboards that give you insights into all aspects of Microsoft Sentinel, and threat intelligence is no exception. You can use the built-in Threat Intelligence workbook to visualize key information about your threat intelligence, and you can easily customize the workbook according to your business needs. You can even create new dashboards combining many different data sources so you can visualize your data in unique ways. Since
Microsoft Sentinel workbooks are based on Azure Monitor workbooks, there is already extensive documentation available, and many more templates.
C: What is a threat intelligence report?
Defender for Cloud's threat protection works by monitoring security information from your Azure resources, the network, and connected partner solutions. It analyzes this information, often correlating information from multiple sources, to identify threats.
Defender for Cloud has three types of threat reports, which can vary according to the attack. The reports available are:
Activity Group Report: provides deep dives into attackers, their objectives, and tactics.
Campaign Report: focuses on details of specific attack campaigns.
Threat Summary Report: covers all of the items in the previous two reports.
This type of information is useful during the incident response process, where there's an ongoing investigation to understand the source of the attack, the attackerג€™s motivations, and what to do to mitigate this issue in the future.
Incorrect:
Not B: When to use Jupyter notebooks
While many common tasks can be carried out in the portal, Jupyter extends the scope of what you can do with this data.
For example, use notebooks to:
Perform analytics that aren't provided out-of-the box in Microsoft Sentinel, such as some Python machine learning features
Create data visualizations that aren't provided out-of-the box in Microsoft Sentinel, such as custom timelines and process trees
Integrate data sources outside of Microsoft Sentinel, such as an on-premises data set.
Not D: Defender for Cloud offers security alerts that are powered by Microsoft Threat Intelligence. It also includes a range of advanced, intelligent, protections for your workloads. The workload protections are provided through Microsoft Defender plans specific to the types of resources in your subscriptions. For example, you can enable Microsoft Defender for Storage to get alerted about suspicious activities related to your Azure Storage accounts.
Reference:
https://docs.microsoft.com/en-us/azure/sentinel/understand-threat-intelligence https://docs.microsoft.com/en-us/azure/defender-for-cloud/defender-for-cloud-introduction https://docs.microsoft.com/en-us/azure/defender-for-cloud/threat-intelligence-reports https://docs.microsoft.com/en-us/azure/sentinel/notebooks

Question 3
A customer is deploying Docker images to 10 Azure Kubernetes Service (AKS) resources across four Azure subscriptions.
You are evaluating the security posture of the customer.
You discover that the AKS resources are excluded from the secure score recommendations.
You need to produce accurate recommendations and update the secure score.
Which two actions should you recommend in Microsoft Defender for Cloud? Each correct answer presents part of the solution.
NOTE: Each correct selection is worth one point.
A. Enable Defender plans.
B. Configure auto provisioning.
C. Add a workflow automation.
D. Assign regulatory compliance policies.
E. Review the inventory.


Answer : BD

D: How are regulatory compliance standards represented in Defender for Cloud?
Industry standards, regulatory standards, and benchmarks are represented in Defender for Cloud's regulatory compliance dashboard. Each standard is an initiative defined in Azure Policy.
To see compliance data mapped as assessments in your dashboard, add a compliance standard to your management group or subscription from within the
Security policy page.
When you've assigned a standard or benchmark to your selected scope, the standard appears in your regulatory compliance dashboard with all associated compliance data mapped as assessments.
B: Configure Defender for Containers components
If you disabled any of the default protections when you enabled Microsoft Defender for Containers, you can change the configurations and reenable them via auto provisioning.
1. To configure the Defender for Containers components:
2. Sign in to the Azure portal.
3. Navigate to Microsoft Defender for Cloud > Environment settings.
4. Select the relevant subscription.
5. From the left side tool bar, select Auto provisioning.
6. Ensure that Microsoft Defenders for Containers components (preview) is toggled to On.



Incorrect:
Not A: When you enable Microsoft Defender for Containers, Azure Kubernetes Service clusters, and Azure Arc enabled Kubernetes clusters (Preview) protection are both enabled by default.
To upgrade to Microsoft Defender for Containers, open the Defender plans page in the portal and enable the new plan:


Not C: No need for automation.
Note: Automate responses to Microsoft Defender for Cloud triggers.
Every security program includes multiple workflows for incident response. These processes might include notifying relevant stakeholders, launching a change management process, and applying specific remediation steps. Security experts recommend that you automate as many steps of those procedures as you can.
Automation reduces overhead. It can also improve your security by ensuring the process steps are done quickly, consistently, and according to your predefined requirements.
Reference:
https://docs.microsoft.com/en-us/azure/defender-for-cloud/update-regulatory-compliance-packages https://docs.microsoft.com/en-us/azure/defender-for-cloud/workflow-automation

Question 4
Your company has an office in Seattle.
The company has two Azure virtual machine scale sets hosted on different virtual networks.
The company plans to contract developers in India.
You need to recommend a solution provide the developers with the ability to connect to the virtual machines over SSL from the Azure portal. The solution must meet the following requirements:
✑ Prevent exposing the public IP addresses of the virtual machines.
✑ Provide the ability to connect without using a VPN.
✑ Minimize costs.
Which two actions should you perform? Each correct answer presents part of the solution.
NOTE: Each correct selection is worth one point.
A. Create a hub and spoke network by using virtual network peering.
B. Deploy Azure Bastion to each virtual network.
C. Deploy Azure Bastion to one virtual network.
D. Create NAT rules and network rules in Azure Firewall.
E. Enable just-in-time VM access on the virtual machines.


Answer : AC

Azure Bastion is deployed to a virtual network and supports virtual network peering. Specifically, Azure Bastion manages RDP/SSH connectivity to VMs created in the local or peered virtual networks.
Note: Azure Bastion is a service you deploy that lets you connect to a virtual machine using your browser and the Azure portal. The Azure Bastion service is a fully platform-managed PaaS service that you provision inside your virtual network. It provides secure and seamless RDP/SSH connectivity to your virtual machines directly from the Azure portal over TLS. When you connect via Azure Bastion, your virtual machines don't need a public IP address, agent, or special client software.
Incorrect:
Not B: Two Azure Bastions would increase the cost.
Reference:
https://docs.microsoft.com/en-us/azure/bastion/bastion-overview

Question 5
HOTSPOT -
You are designing security for a runbook in an Azure Automation account. The runbook will copy data to Azure Data Lake Storage Gen2.
You need to recommend a solution to secure the components of the copy process.
What should you include in the recommendation for each component? To answer, select the appropriate options in the answer area.
NOTE: Each correct selection is worth one point.
Hot Area:



Answer : 

Box 1: Azure Web Application Firewall with network service tags
A service tag represents a group of IP address prefixes from a given Azure service. Microsoft manages the address prefixes encompassed by the service tag and automatically updates the service tag as addresses change, minimizing the complexity of frequent updates to network security rules.
You can use service tags to define network access controls on network security groups, Azure Firewall, and user-defined routes.
Incorrect:
* Not Azure private link with network service tags
Network service tags are not used with Private links.
Box 2: Automation Contributor built-in role
The Automation Contributor role allows you to manage all resources in the Automation account, except modifying other user's access permissions to an
Automation account.
Reference:
https://docs.microsoft.com/en-us/azure/virtual-network/service-tags-overview https://docs.microsoft.com/en-us/azure/automation/automation-role-based-access-control

