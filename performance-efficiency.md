# Performance Efficiency Best Practices

## Selection

### PRF_SEL_x: Pick the Right Compute Option

Test your security server performance to pick the best instance or compute type to run your security server workload.
Additionally, consider how the security server fits into your service development and operations landscape. For example,
if you are looking to deploy a standalone security server in front of multiple services and the security server would
be managed by a dedicated team experienced in server administration, deploying as an EC2 instance could be the best fit.
On the other hand, if the security server is directly coupled to a single containerized service and would benefit from sharing 
deployment and operations best practices with the service, deploying the security server sidecar container on top of 
either Elastic Container Service (ECS) or Elastic Kubernetes Service (EKS) would be the best way to go.

For EC2-based security servers:
- c5.large, c5a.large for better CPU performance at a lower cost
- t3.medium, t3a.medium for a better price point when there's no sustained load on the CPU
- m5.large, m5a.large when running low on memory

For ECS and EKS based container deployments:
- Prefer Fargate as the compute engine to reduce server management overhead.
- If Fargate is not an option, use the same guidance as for EC2-based security servers when picking a container host.

**Recommended tools:**
* [Amazon EC2](https://aws.amazon.com/ec2)
* [Amazon Elastic Container Service](https://aws.amazon.com/ecs)
* [Amazon Elastic Kubernetes Service](https://aws.amazon.com/eks)


### PRF_SEL_x: Pick the Right Database Option

Prefer AWS-managed database services over self-managed database options. Use Amazon Aurora PostgreSQL or Amazon Aurora
Serverless (where available), for best availability and minimal management requirements.

**Recommended tools:**
* [Amazon Aurora](https://aws.amazon.com/rds/aurora/)
* [Amazon Aurora Serverless](https://aws.amazon.com/rds/aurora/serverless/)

## Review

### PRF_REV_x: Evaluate Performance Over Time

Stay up-to-date on new resources and services. Evaluate ways to improve performance as new instance types, compute
options or database services are launched.

## Monitoring

### PRF_MON_x: Monitor Your Resources for Performance

Measure the performance characteristics of your security servers over time and use this information to adjust the
infrastructure setup of your X-Road environments. Analyze metrics when events or incidents occur, to understand and
diagnose the impact. Establish Key Performance Indicators, such as API latency, to quantify the performance experience
expected by your customers.

**Recommended tools:**
* [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/)

---

**Previous Topic:** [Reliability](reliability.md)

**Next Topic:** [Cost Optimization](cost-optimization.md)