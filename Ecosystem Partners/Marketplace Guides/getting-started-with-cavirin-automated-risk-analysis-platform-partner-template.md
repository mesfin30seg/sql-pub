{{{
"title": "Getting Started with Cavirin Automated Risk Anaylysis Platform - Partner Template",
"date": "06-30-2015",
"author": "<a href='https://www.linkedin.com/in/bstolzberg'>Bob Stolzberg</a>",
"attachments": [],
"contentIsHTML": false
}}}

![Cavirin Logo](../../images/Ecosystem-Cavirin-ARAP_logo_full-color_200px.png)

### Partner Profile
Cavirin - Delivering Continuous Audit and Operational Compliance to the Cloud

For additional information about the company please visit [Cavirin](http://www.cavirin.com).

#### Contact Cavirin
##### Cavirin Sales and Support:
* 24x7 Web Support - [https://support.cavirin.com](https://support.cavirin.com)
* 24x7 Email Support - [support@cavirin.com](mailto:support@cavirin.com)
* Sales Telephone Support - Please email [Sales](mailto:sales@cavirin.com) or via telephone: 1-408-200-3544 option 2

### Description
Cavirin has integrated their technology with the Lumen Cloud platform. The purpose of this KB article is to help the reader take advantage of this integration to achieve rapid time-to-value for this compliance and regulatory governance solution.

Cavirin gives you visibility across your entire IT ecosystem. It supports the broadest range of devices and vendors on the market, so nothing escapes notice. It searches out outdated and unpatched servers, the number one culprit implicated in major IT security breaches. It checks your firewall and OS configurations against best practices and regulatory policies. But it doesn’t stop there. Cavirin also monitors your accounts ensuring tight access control, strict password and lockout policies, and unused accounts.

Technology from Cavirin helps Lumen Cloud customers address the business challenge of compliance and regulatory governance for their entire IT environment by providing continuous discovery and device review. Now available as part of the Lumen Cloud Blueprint Engine.

It's easy! Think of Cavirin as your operational GRC tool in the cloud.

### Solution Overview
Cavirin is a security and compliance solution expressly designed for cloud AND data center environments-the ultimate hybrid cloud solution. Cavirin provides a range of compliance guidelines, expressly designed to measure and monitor risk associated with these compliance guidelines (PCI, HIPAA, ISO, NIST, SOC 2, CIS, and/or DISA STIGs) that are applied to your environment. In addition to OS-level checks, Cavirin can also evaluates application-specific CIS guidelines, such as those for Microsoft IIS, Internet Explorer, SQL Server, Firefox, Oracle, and MySQL. Lastly, we are an extremely viable solution for File Integrity Monitoring for your hybrid cloud as well.

Cavirin is designed to assist security and compliance teams who face regulatory audits, and greatly reduces the manual effort in audit preparation, execution and maintenance in perpetuity. A key benefit of Cavirin is that it is platform-independent, and was designed to reach and support a wide range of platforms.

### Offer
Cavirin has provided their Automated Risk Analysis Platform virtual appliance - called a Partner Template - that can be deployed to your Lumen Cloud account via a Service Task. Although Service Tasks are ordinarily billed to the end user account, Lumen will provide a refund for the Service Task costs associated with deploying the Cavirin Partner Template. Cavirin is sold on a per device basis and broken into tiers. We also have trial licenses available upon request. To receive pricing for your environment and/or receive a trial license please contact Cavirin sales: [Tim Thompson](mailto:tthompson@cavirin.com) or via telephone: (469) 831-8357.

### Audience
Lumen Cloud Users

### Impact
After executing the steps in this Getting Started document, the users will have a functioning Cavirin Automated Risk Analysis Platform (ARAP) upon which they can start developing discovery solutions.

Customers can access the Cavirin Help Center by going to [Cavirin Support](https://support.cavirin.com) to access articles and how-to videos.

This deployment process for Partner Templates currently requires manual interaction via the Service Task process, but will be further automated in future releases of the Lumen Cloud Platform.


### Prerequisite
* Access to the Lumen Cloud platform as an authorized user.
* Identify a Network VLAN you want the Cavirin partner template to reside on.
* A Cavirin ARAP License. You will need to send this to Lumen Support at the time of deployment.
* The Cavirin ARAP server will utilize the following resources. Note: larger environments may require additional processors to allow for speed of discovery.
  *  8GB RAM
  *  2 Processors
  *  100GB disk space (can be thin provisioned)
  *  line of sight network access to devices in scope
* The following protocols are used for discovery.
  * ICMP
  * SNMP
  * SSH
  * WMI / Windows Remote Management (WinRM)
* To access Windows machines you will need Administrator credentials.
* To access Linux machines you will need root level credentials, a PEM key file can also be used for access.
* If you would like to access systems outside the immediate network then there must routable access to that network either through a router or VPN.
* Please refer to [Cavirin Support](https://support.cavirin.com) to find any additional prerequisites required for your deployment.

### Postrequisite
If you want to access your Cavirin partner template over the internet, please perform the following tasks once your VM has been deployed to your account.
* [Add a Public IP](../../Network/Lumen Cloud/how-to-add-public-ip-to-virtual-machine.md) to your server through the Control Portal.
* If required, [allow incoming traffic for the admin port](../../Network/Lumen Cloud/how-to-add-public-ip-to-virtual-machine.md) by clicking on the Servers Public IP in the Control Portal.
* **IMPORTANT**: Please make sure your firewall rules are properly configured to only allow specific source traffic. If you do not configure source traffic rules you risk exposing your VM to the entire internet. Note: When accessing your VM for the first time or for any administration, we recommend you connect to your Lumen Cloud environment via Client VPN.

### Detailed Steps to Deploy Cavirin Automated Risk Analysis Platform
The Cavirin partner template deploys in a virtual appliance model, as a Lumen Cloud *Partner Template*. Follow these step by step instructions to deploy a Cavirin partner template in to your Lumen Cloud account:

* Open a service task request ticket via email to [help@ctl.io](mailto:help@ctl.io) with the following details. *You will need to edit some of the information below and attach your Cavirin license to the email!*

----
TO: help@ctl.io

EMAIL SUBJECT:   Ecosystem Partner Template Import Request

CLC Support Team,

Please create a ticket to import the Ecosystem Partner Template image  referenced below to my Lumen Cloud Account:

- Import Lumen Ecosystem Partner Source Image: Cavirin OVA
- My Lumen Cloud Account Alias: ####
- My Lumen Cloud Account PIN:  ######
- Data Center to import image to: ###
- Server Name to import image as: ##########
- VLAN in the account to add the Server to: ########
- Additional Notes or work to be done: Attached to this email is my Cavirin License that you'll need during setup

Please let me know if you have any questions or issues. Kindly send me a reply once the work has been completed and let us know the IP address of the server where this technology has been deployed.

Thank you very much,

Your_Name_Here

-----

### Pricing
There are no Cavirin license costs included. The cost to deploy the Cavirin Partner Template will be billed as a Service Task, but Lumen will provide a credit for those costs. In order to receive a credit, please follow the instructions below. More information about Service Tasks and fees is [available here](http://www.ctl.io/service-tasks).

#### Process to request credit for Service Task fee
Follow this process to request credit on your account to re-imburse any expense to deploy the Partner Template.

* Please copy and paste the email below and send it to [ECOSystem@centurylink.com](mailto:ECOSystem@centurylink.com)

----

TO: ECOSystem@centurylink.com

EMAIL SUBJECT:   Requesting Credit for Cavirin Partner Template Deployment

CLC Ecosystem Team,

I am requesting a credit be placed on my account to cover the fees associated with deploying the Cavirin Partner Template to my account under the Service Task deployed on MM/DD/YYYY. My Lumen Cloud username or account alias the credit needs to be placed on is ######

Thank you very much, your_name_here

----

### Accessing and Configuring your Cavirin partner template
Follow these steps to access and configure your Cavirin partner template:
1. Using a web browser, Go to https://server_ip_address. (This can be the private IP if you are connected via VPN, or a Public IP if you added one and opened the proper firewall rules.)
2. Log in with newly created administrator account.
3. Once logged in you start creating discovery profiles to scan your devices.
4. Refer to [Cavirin Support](http://support.cavirin.com) for additional how-to information, a user account will be required, please contact [support@cavirin.com](mailto:support@cavirin.com) to request access.

### Frequently Asked Questions

#### Where do I obtain my Cavirin License or entitlements?
Existing Lumen Enterprise Customers can contact their Account Representative for help obtaining a Cavirin license, or contact Cavirin directly: Please email [Tim Thompson](mailto:tthompson@cavirin.com) or via telephone: (469) 831-8357

#### Who should I contact for support?
* For issues regarding the Cavirin appliance, the application or functionality of it, please contact Cavirin via their 24x7 Web Support: [Cavirin Support](https://support.cavirin.com), or via Email Support: [support@cavirin.com](mailto:support@cavirin.com).
* For issues related to cloud infrastructure (VMs, network, etc.), or if you experience a problem deploying the Blueprint, please open a Lumen Cloud Support ticket by emailing [help@ctl.io](mailto:help@ctl.io) or [through the support website](https://t3n.zendesk.com/tickets/new).
