# Week 5 Quiz - Day 9 and Day 10

This quiz contains 10 original questions covering yesterday's Auto Scaling and
Launch Templates session and today's Elastic Load Balancing session. Choose one
answer for each question before checking the answer key.

## Day 9 - Auto Scaling and Launch Templates

### Question 1

What is the main responsibility of an EC2 Launch Template?

- A. Decide how many instances must run
- B. Define how each EC2 instance is configured
- C. Monitor application health
- D. Distribute requests between instances

### Question 2

An Auto Scaling group has minimum `1`, desired `2`, and maximum `4`. How many
instances does it normally try to maintain right now?

- A. 1
- B. 2
- C. 4
- D. It always chooses a random value between 1 and 4

### Question 3

A company wants its fleet's average CPU utilization to remain near 50%. Which
scaling policy is the simplest suitable choice?

- A. Scheduled scaling
- B. Predictive scaling only
- C. Target tracking
- D. Manual scaling

### Question 4

An EC2 instance is running, but nginx has stopped and the health endpoint
fails. Which health check allows the Auto Scaling group to detect this
application failure?

- A. EC2 status check only
- B. ELB health check
- C. IAM Access Analyzer
- D. EBS volume status

### Question 5

A new tested AMI has been added as a new Launch Template version. What should
be used to replace existing fleet instances gradually?

- A. Instance Refresh
- B. Security Group propagation
- C. Deregistration delay
- D. Route-table replacement

## Day 10 - Elastic Load Balancing

### Question 6

Which load balancer should be selected for HTTP host-based and path-based
routing?

- A. Network Load Balancer
- B. Gateway Load Balancer
- C. Application Load Balancer
- D. NAT Gateway

### Question 7

A TCP application requires a static public IP address in each enabled
Availability Zone. Which option best meets the requirement?

- A. ALB with path rules
- B. Internet-facing NLB with an Elastic IP per AZ
- C. GWLB with nginx targets
- D. CloudWatch alarm

### Question 8

An ALB listener rule sends traffic to Blue with weight 80 and Green with weight
20. After 10 requests, the learner sees 7 Blue and 3 Green responses. What is
the best explanation?

- A. The weights are broken
- B. Weighted routing is approximate, especially with a small sample
- C. Green must always receive exactly two requests out of every ten
- D. The ALB is operating at Layer 4

### Question 9

What happens while an ALB target is in the `Draining` state?

- A. It receives all new requests
- B. It immediately deletes its EC2 instance
- C. It receives no new requests while existing connections may finish
- D. It automatically becomes a Gateway Load Balancer appliance

### Question 10

Which design is correct for transparent insertion of a compatible firewall or
IDS/IPS appliance fleet?

- A. ALB using HTTP path rules
- B. NLB using target stickiness
- C. GWLB using GENEVE on UDP `6081` and symmetric routing
- D. Auto Scaling without a target group

## Answer Key

| Question | Answer | Explanation |
|---:|:---:|---|
| 1 | B | A Launch Template defines AMI, instance type, storage, networking, IAM, metadata, and User Data settings. |
| 2 | B | Desired capacity is the number the group currently attempts to maintain. |
| 3 | C | Target tracking adjusts capacity to keep a selected metric near its target. |
| 4 | B | ELB health checks test the application endpoint, not only the EC2 infrastructure state. |
| 5 | A | Instance Refresh performs a controlled replacement using the desired Launch Template configuration. |
| 6 | C | ALB operates at Layer 7 and evaluates HTTP host and path conditions. |
| 7 | B | An internet-facing NLB can use one Elastic IP for each enabled AZ. |
| 8 | B | Weights represent probability, so small samples rarely produce an exact split. |
| 9 | C | Deregistration delay allows active connections to finish while preventing new requests. |
| 10 | C | GWLB inserts compatible appliances using GENEVE and requires a symmetric traffic path. |

## Score Guide

| Score | Result |
|---:|---|
| 9-10 | Strong understanding - ready for scenario practice |
| 7-8 | Good foundation - revise the missed decisions |
| 5-6 | Review the Week 5 theory and lab observations |
| 0-4 | Repeat Day 9 and Day 10 revision before the Mini-Mock |

Do not memorize only the answer letter. Explain why the selected service meets
the requirement and why the other choices do not.
