{{{
  "title": "Partner Cloud Integration: Lumen AWS Reserved Instance and Savings Plan Strategy",
  "date": "04-02-2020",
  "author": "Ben Swoboda",
  "attachments": [],
  "contentIsHTML": false
}}}

### Overview

Lumen [Cloud Application Manager's](https://www.ctl.io/cloud-application-manager/) offers [consolidated billing](partner-cloud-integration-consolidated-billing.md) to make it easy to pay for resources across the entire hybrid cloud. Part of the consolidated billing involves Lumen's approach for billing Amazon Web Services [Reserved Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-reserved-instances.html).


### Audience

Users of Cloud Application Manager that already have, or are considering, an existing AWS account under Lumen consolidated billing.  In addition, users of Cloud Application Manager that are considering new AWS accounts created through Cloud Application Manager.  These users will want to understand some important guidelines for how Cloud Application Manager supports billing for AWS Reserved Instances and Cost Savings Plans. 

### Prerequisites

For a new AWS Account:

* The customer must have reviewed the process for creating a [new Amazon Web Services account](partner-cloud-integration-aws-new.md) and is thinking about buying AWS Reserved Instances.

For an existing AWS Account:

* The customer must already have an AWS account that has been specifically authorized by AWS for transfer. (Only approved accounts are authorized for this process.)

* The customer must have reviewed the process for transferring an [existing Amazon Web Services account](partner-cloud-integration-aws-existing.md)

* The customer has purchased or is thinking about buying AWS Reserved Instances or Cost Savings Plans.


### Important Information

#### Customer Reserved Instances

Reserved Instances or Cost Savings Plans purchased prior to transferring to Lumen may still be used and must always stay with the account at which they were purchased.  If the Customer purchased Reserved Instances or Cost Savings Plans from a Master Payer they own, they can still use them while under Lumen Cloud Application Manager Consolidated Billing. Please review the process for migrating an [existing Amazon Web Services account](partner-cloud-integration-aws-existing.md), specifically the "Considerations" section.

All customers should understand that their AWS accounts will reside under one single Lumen-owned AWS Organization.

The Lumen AWS Organization provides safeguard policies to ensure that customers receive the full cost benefits of their AWS Reserved Instances have been purchased. These policies also apply to Reserved Instances or Cost Savings Plans that existed before the account was migrated to Lumen.

If a Cloud Application Manager user wants to purchase Reserved Instances or Cost Savings Plans which exceed the limit prescribed by AWS, please contact [Cloud Application Manager Support](https://www.ctl.io/cloud-application-manager/#Support) with your request.

(Please note that Reserved Instances do not apply to the Lumen 5% EC2 OnDemand Discount)

#### Initial Purchase Fee
Lumen Cloud Application Manager allows customers to buy Reserved Instances or Cost Savings Plans through the AWS Console and choose between three payment options: All Upfront, Partial Upfront, and No Upfront.

Users that choose the "Partial" or "All Upfront" payment option should understand that the initial purchase fee will be shown as a different line the your Lumen bill.

Lumen splits the different products, against which RI's and or Cost Savings Plans can be purchased, into two different categories: Software as a Service(SaaS) and Infrastructure as a Service(IaaS). These monthly increments are displayed on the customer's Cloud Application Manager bill with the line item description below and will be displayed as IaaS or SaaS depending on the product category. Cost Savings Plans will be included in the Reserve Instance line item on invoices. Further detail to explain the charge is provided in CAM's Detailed Usage History.


Line item description on the bill: *Integrated, AWS Reserve Instance Fees - IaaS*


Line item description on the bill: *Integrated, AWS Reserve Instances - SaaS*



#### Monthly Increments

Customers who buy an AWS Reserved Instance or Cost Savings Plan with the Partial or No Upfront payment options pay the remaining balance in monthly increments over the term of the RI or Cost Savings Plan . These monthly increments are displayed on the bill with the line item description below. Cost Savings Plans will be included in the Reserve Instance line item on invoices. Further detail to explain the charge is provided in CAM's Detailed Usage History.

Line item description on the bill: *AWS Monthly EC2 Reserved Instance Charges*


#### Reserved Instance (RI) Monthly Increments that are not EC2
AWS continues to expand the different products that are available to purchase Reserved Instances. Lumen adapts to these changes by enabling any non-EC2 RI to be displayed on the bill with the line item description below.

Line item description on the bill: *Integrated, AWS Reserve Instances - SaaS*


### Contacting Cloud Application Manager Support

We???re sorry you???re having an issue in [Cloud Application Manager](https://www.ctl.io/cloud-application-manager/). Please review the [troubleshooting tips](../Troubleshooting/troubleshooting-tips.md), or contact [Cloud Application Manager support](mailto:incident@CenturyLink.com) with details and screenshots where possible.

For issues related to API calls, send the request body along with details related to the issue.
