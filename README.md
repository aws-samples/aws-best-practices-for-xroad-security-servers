# Best Practices for Deploying X-Road Security Servers on AWS

[X-Road®](https://x-road.global/) is an open-source solution for secure data exchange between organizations.
Data is exchanged on X-Road through access points called Security Servers 
(see: [X-Road Architecture](https://x-road.global/architecture)), implementing the same technical specifications.
Security Servers are required for both producing and consuming data and services via X-Road.

## Before Getting Started

Before you start planning on running your X-Road Security Server and Information System on AWS, take a look at the 
[Before Getting Started](FAQ.md#before-getting-started) section on the [Frequently Asked Questions](FAQ.md) page. 

## Best Practices

This project discusses the best practices for deploying X-Road Security Servers on AWS through the lens of 
[AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected). The AWS Well-Architected 
Framework describes the key concepts, design principles, and architectural best practices for designing and running 
workloads in the cloud. The AWS Well-Architected Framework consists of five pillars that are covered in different 
sections of this project.

### [Operational Excellence](operational-excellence.md)

The operational excellence pillar focuses on running and monitoring systems to deliver business value, and continually 
improving processes and procedures. Key topics include automating changes, responding to events, and defining 
standards to manage daily operations.

### [Security](security.md)

The security pillar focuses on protecting information and systems. Key topics include confidentiality and integrity of 
data, identifying and managing who can do what with privilege management, protecting systems, and establishing controls 
to detect security events.

### [Reliability](reliability.md)

The reliability pillar focuses on ensuring a workload performs its intended function correctly and consistently when 
it’s expected to. A resilient workload quickly recovers from failures to meet business and customer demand. Key topics 
include distributed system design, recovery planning, and how to handle change.

### [Performance Efficiency](performance-efficiency.md)

The performance efficiency pillar focuses on using IT and computing resources efficiently. Key topics include selecting 
the right resource types and sizes based on workload requirements, monitoring performance, and making informed decisions 
to maintain efficiency as business needs evolve.

### [Cost Optimization](cost-optimization.md)

The cost optimization pillar focuses on avoiding unnecessary costs. Key topics include understanding and controlling 
where money is being spent, selecting the most appropriate and right number of resource types, analyzing spend over 
time, and scaling to meet business needs without overspending.

## Getting Started

Refer to the [Getting Started with AWS](https://aws.amazon.com/getting-started/) guide for more information about the 
AWS Cloud and how to launch your first workloads on AWS. 

X-Road Security Servers can be launched on [Amazon EC2](https://aws.amazon.com/ec2) Instances - see the [AWS Quick Start Guide for launching a Linux Virtual Machine](https://docs.aws.amazon.com/quickstarts/latest/vmlaunch/welcome.html) and the X-Road [Security Server Installation Guide for Ubuntu](https://docs.x-road.global/Manuals/ig-ss_x-road_v6_security_server_installation_guide.html) 
for more details on how to set up a Security Server on an Ubuntu Linux instance.

Alternatively, [X-Road Security Server Sidecar](https://hub.docker.com/r/niis/xroad-security-server-sidecar/) containers 
can be launched on [Amazon Elastic Container Service](https://aws.amazon.com/ecs) or on [Amazon Elastic Kubernetes Service](https://aws.amazon.com/eks/). 
See the [Security Server Sidecar User Guide](https://github.com/nordic-institute/X-Road/blob/develop/doc/Sidecar/security_server_sidecar_user_guide.md)
and the [Kubernetes Security Server Sidecar User Guide](https://github.com/nordic-institute/X-Road/blob/develop/doc/Sidecar/kubernetes_security_server_sidecar_user_guide.md) 
for more details.

Consider [Amazon RDS for PostgreSQL](https://aws.amazon.com/rds/postgresql) or [Amazon Aurora](https://aws.amazon.com/rds/aurora)
for a Security Server remote database setup option, instead of hosting and managing your own.

For hands-on tutorials on compute, containers and databases, take a look at the 
[Getting Started Resource Center](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23compute%7Ccategory%23containers%7Ccategory%23databases&awsf.getting-started-content-type=content-type%23hands-on&?e=gs2020&p=gsrc&getting-started-all.sort-by=item.additionalFields.sortOrder&getting-started-all.sort-order=asc&awsf.getting-started-level=*all).

## I Have More Questions

See the [Frequently Asked Questions](FAQ.md) page for common questions and answers about running your X-Road workloads
on AWS. If you can't get a satisfying answer from there, [Join the X-Road Community](https://x-road.global/community) to
meet X-Road enthusiasts around the world and ask for help.

This guide is not intended to provide step-by-step instructions of setting up a Security Server on AWS, as the process
can vary significantly on your use case. If you feel you need guidance on getting started or someone to take you 
through the process end-to-end, reach out to the [X-Road Community](https://x-road.global/community) or to   
[X-Road Technology Partners](https://x-road.global/xroad-technology-partners-companies) for further help.

If you think that there are crucial design guidelines missing from this guide, feel free to 
[open an issue](https://github.com/aws-samples/aws-best-practices-for-xroad-security-servers/issues/new) and
describe what's missing in as much detail as you can.

## Contributing to this Project

We welcome community contributions as pull requests. See [CONTRIBUTING](CONTRIBUTING.md) for more information.

### General Improvements

Before submitting a pull request for change in content (e.g. proposing a new best practice or removing one, changing
diagrams, adding or removing content from an existing best practice), 
please [open an issue](https://github.com/aws-samples/aws-best-practices-for-xroad-security-servers/issues/new) to 
discuss the improvement in detail. For minor changes in formatting or correcting typographical errors, you can open
a pull request directly.

### Reporting Issues

The best way to contact the team or to report an issue with the content is through GitHub. 
You can [open an issue](https://github.com/aws-samples/aws-best-practices-for-xroad-security-servers/issues/new) and 
describe the issue in as much detail as you can.

### Reporting Security Concerns

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information on how to report security related
issues.

## License Summary

The documentation is made available under the Creative Commons Attribution-ShareAlike 4.0 International License. 
See the [LICENSE](LICENSE-SAMPLECODE) file.

The sample code within this documentation is made available under the MIT-0 license. 
See the [LICENSE-SAMPLECODE](LICENSE-SAMPLECODE) file.
