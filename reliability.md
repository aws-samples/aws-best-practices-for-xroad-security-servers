# Reliability Best Practices

## Architecture

### REL_ARC_01: Define Recovery Time and Point Objectives

Understand the criticality of your X-Road infrastructure to your customers - internal and external. Define how fast
do you need to recover from a failure (Recovery Time Objective, RTO) and how much data loss can you tolerate (Recovery
Point Objective, RPO). Adjust your backup methods and frequency accordingly. Align these objectives with the objectives
of your customers to avoid X-Road infrastructure becoming the weakest link in the system, but also to avoid cost 
overheads.

**Recommended tools:**
* [Example Implementations for Availability Goals](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/example-implementations-for-availability-goals.html)


### REL_ARC_02: Separate Compute and Storage

By separating storage from the compute layer, it becomes easier to replace and scale each separately. For Security Servers
running as EC2 instances, you can pick between EBS volumes or EFS file systems for storage. With sidecar container deployments, 
mounting EFS file systems is the best option for persistent storage. 

Prefer using an Amazon RDS database over the built-in PostgreSQL option for best performance and availability. Consider
sharing an RDS cluster between multiple Security Servers over setting up an RDS cluster per Security Server. RDS supports multiple availability zones out of the box, which makes them highly available and reliable even in case of an availability zone failure. More info for RDS multi AZ support [here](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)

**Recommended tools:**
* [Amazon Elastic Block Store](https://aws.amazon.com/ebs/)
* [Amazon Elastic File System](https://aws.amazon.com/efs/)
* [Amazon Relational Database Service](https://aws.amazon.com/rds/)

### REL_ARC_03: Scale Horizontally to Increase Availability

Instead of one large Security Server, deploy multiple small ones to reduce the impact of a single failure on the 
overall workload. Distribute requests across Security Servers to ensure that they don’t share a common point of 
failure. Additionaly ensure that the when creating mutiple instances of the security server the instances are spread across different availability zones for high availability and reliability. How to do cross zone load balancing can be found [here](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/how-elastic-load-balancing-works.html)

**Recommended tools:**
* [Amazon EC2 Auto Scaling Groups](https://docs.aws.amazon.com/autoscaling/ec2/userguide/AutoScalingGroup.html)

## Change Management

### REL_CHM_01: Integrate Testing as Part of Your Deployment

Before deploying an updated version of a Security Server to a production environment, deploy it in a test environment.
Run automated integration tests that involve connecting to / from the subsystem(s) behind the Security Server. 
Verify that the Security Server management UI is available for operator access. When tests succeed, deploy the changes
into a production environment.

### REL_CHM_02: Deploy Using Immutable Infrastructure

Prefer separately staged changes to the Security Servers to in-place changes. Build Security Server images periodically
up-front in an automated build pipeline to get the latest versions of required operating system packages. Disable 
automatic in-place upgrades of packages on the Security Server in favor of replacing the Security Servers from the
latest verified machine image.

**Recommended tools:**
* [Amazon Machine Images](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html)

### REL_CHM_3: Deploy With Automation

Minimize the risk of human error by automating Security Server deployments. Automate both roll-forward and roll-back
scenarios, such that any deployment can be stopped and reverted when needed. Integrate deployment automation with 
canary tests, such that you can assess system health during and after the deployment has occurred. 

## Failure Management

### REL_FLM_01: Back Up Data

Configure automatic backups for Security Server databases, through RDS snapshots and point-in-time recovery. Configure
logs to be backed up to S3 in addition to CloudWatch for auditing purposes. Periodically verify that backups can be
used in a disaster recovery scenario. Also, don't forget to transfer the message log archive files to an external
storage, for example, EFS file system or S3 bucket.

Recommended tools:
* [Amazon RDS Backups](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html)

### REL_FLM_02: Design to Withstand Component Failures

Run at least two Security Server instances behind a load balancer in separate availability zones, with at least two 
database instances (writer and reader) in the same availability zones for lowest latency and minimum downtime in the 
situation of component failure. Configure health checks on Security Servers to allow for the auto-scaling group to 
replace a failed instance.

For sidecar Security Servers (container-based deployments), define your workload as an ECS or EKS service, to let
the container platform manage the lifecycles of Security Server containers.

### REL_FLM_03: Test Reliability

Periodically verify recovery procedures. Adopt chaos engineering principles to introduce failures in your security
server environment. Verify that you can quickly recover from database failures or corruptions. Verify recovery from
the loss of a single Security Server instance.

**Recommended tools:**
* [AWS Fault Injection Simulator](https://aws.amazon.com/fis/)

---

**Previous Topic:** [Security](security.md)

**Next Topic:** [Performance Efficiency](performance-efficiency.md)
