{{{
  "title": "Supported Operating Systems",
  "date": "11-25-2019",
  "author": "Matthew Ordman",
  "attachments": [],
  "contentIsHTML": false
}}}

### What operating systems are supported in the Lumen Cloud?

The following operating systems are supported in Lumen Cloud:

Virtual Machines|Bare Metal
----------------|----------
CentOS 6<br>CentOS 7<br>Debian 6<br>Debian 7<br>RedHat Enterprise Linux 5<br>RedHat Enterprise Linux 6<br>RedHat Enterprise Linux 7<br>Ubuntu 14<br>Ubuntu 16<br>Ubuntu 18<br>Windows Server 2012 Datacenter Edition<br>Windows Server 2012 R2 Datacenter Edition<br>Windows Server 2016 Datacenter Edition<br>Windows Server 2019 Datacenter Edition|Windows 2012 R2 Standard Edition<br>Windows 2012 R2 Datacenter Edition<br>Red Hat Enterprise Linux 6<br>Red Hat Enterprise Linux 7<br>CentOS 6<br>CentOS 7<br>Ubuntu 14<br>Ubuntu 16

**NOTE: Only the 64-bit version of each OS is supported**

### What does it mean for an operating system to be "supported"?

All supported operating systems have a "template" in Lumen Cloud that is created, maintained, and managed by Lumen Cloud engineers. Templates can be viewed in the "Create Server" screen and accessed via the API. These templates are the basis for all new virtual machines created in the platform.

### Can I build custom templates?

Yes - the only requirement is that each custom template needs to "map" to a supported OS template. For best practices, read this article: ["How To: Create Customer Specific OS Templates"](../Servers/how-to-create-customer-specific-os-templates.md)

### What is your operating system retirement policy?

This is listed [here](../Servers/operating-system-template-retirement-policy.md).

### Can I perform an in-place upgrade of the Operating System?

No, in-place upgrades of the Operating System are not supported.  This means that you cannot, for example, upgrade a Windows Server 2012 Standard edition to Windows Server 2012 Datacenter edition.  It will be necessary to deploy a new server if you need a different OS edition.

### Can I bring my own license?

Currently, CLC does not support a Bring Your Own License model for both Windows and RedHat.

### I'd like to deploy an operating system that is not supported. What are my options?

We do not recommend that you deploy unsupported operating systems in the platform. Lumen Cloud SLAs will not apply to virtual machines running an *unsupported* OS. In addition, some features may not work on unsupported OSes.
