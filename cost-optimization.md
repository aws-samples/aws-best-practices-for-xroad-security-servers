# Cost Optimization Best Practices

## Financial Management

### CST_FNM_x: Quantify Business Value Delivered From Cost Optimization

Quantify how much it costs to receive or send a single X-Road request in your environment. Consider not only the 
infrastructure costs, but also the recurring costs of managing the infrastructure (engineer time) and costs of 
incidents (incident response time, loss of trust / business). Consider environmental impact and sustainability
as a part of delivering business value in a responsible manner.

## Expenditure Awareness

### CST_EXA_x: Monitor Cost and Usage

Use the Billing Console, Cost Explorer with hourly granularity enabled and create a Cost and Usage Report to get the
most accurate view of cost and usage across your entire organization. When possible, assign organization meaning to
cost and usage by tagging your resources. This allows you to understand how your X-Road infrastructure costs relate
to the cost of your entire infrastructure.

**Recommended tools:**
* [AWS Billing and Cost Management](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-what-is.html)

## Cost Effective Resources

### CST_RES_x: Select the Best Pricing Model

AWS has multiple [pricing models](http://aws.amazon.com/pricing/) that allow you to pay for your resources in the most 
cost-effective way that suits your organization’s needs. Use On Demand or Spot capacity (if available) for short-lived 
security server instances, such as extra capacity to handle peak workloads or capacity to run ad hoc testing 
environments. Use Compute Savings Plans or EC2 Instance Savings Plans for the bulk of your security server workload 
to reduce server costs.

**Recommended tools:**
* [Savings Plans](https://aws.amazon.com/savingsplans/)
  
---

**Previous Topic:** [Performance Efficiency](performance-efficiency.md)