# Best Practices for Deploying X-Road Security Servers on AWS

---

[X-Road®](https://x-road.global/) is an open-source solution for secure data exchange between organizations.
Data is exchanged on X-Road through access points called Security Servers 
(see: [X-Road Architecture](https://x-road.global/architecture)), implementing the same technical specifications.
Security Servers are required for both producing and consuming data and services via X-Road.

## Best Practices

This project discusses the best practices for deploying X-Road Security Servers on AWS through the lens of 
[AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected). The AWS Well-Architected 
Framework describes the key concepts, design principles, and architectural best practices for designing and running 
workloads in the cloud.

### [Operational Excellence](security-servers.md#operational-excellence)

The operational excellence pillar focuses on running and monitoring systems to deliver business value, and continually 
improving processes and procedures. Key topics include automating changes, responding to events, and defining 
standards to manage daily operations.

### [Security](security-servers.md#security)

The security pillar focuses on protecting information and systems. Key topics include confidentiality and integrity of 
data, identifying and managing who can do what with privilege management, protecting systems, and establishing controls 
to detect security events.

### [Reliability](security-servers.md#reliability)

The reliability pillar focuses on ensuring a workload performs its intended function correctly and consistently when 
it’s expected to. A resilient workload quickly recovers from failures to meet business and customer demand. Key topics 
include distributed system design, recovery planning, and how to handle change.

### [Performance Efficiency](security-servers.md#performance-efficiency)

The performance efficiency pillar focuses on using IT and computing resources efficiently. Key topics include selecting 
the right resource types and sizes based on workload requirements, monitoring performance, and making informed decisions 
to maintain efficiency as business needs evolve.

### [Cost Optimization](security-servers.md#cost-optimization)

The cost optimization pillar focuses on avoiding unnecessary costs. Key topics include understanding and controlling 
where money is being spent, selecting the most appropriate and right number of resource types, analyzing spend over 
time, and scaling to meet business needs without overspending.


## Contributing to this Project

We welcome community contributions and pull requests. See [CONTRIBUTING](CONTRIBUTING.md) for more information.

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

### Reporting Security Problems

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information on how to report security related
issues.

## License Summary

The documentation is made available under the Creative Commons Attribution-ShareAlike 4.0 International License. 
See the [LICENSE](LICENSE-SAMPLECODE) file.

The sample code within this documentation is made available under the MIT-0 license. 
See the [LICENSE-SAMPLECODE](LICENSE-SAMPLECODE) file.
