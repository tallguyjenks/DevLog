---
id: 6baoi76mio8md4unhxb0105
title: Mastering Chaos a Netflix Guide to Microservices
desc: ''
updated: 1657144390650
created: 1657139845632
url: 'https://youtu.be/CZ3wIuvmHeM'
---

## Challenges and Solutions

### Dependency

#### Intra-service Requests

- Microservice A talking to Microservice B
- Problems
  - Network Latency, Congestion, failure
  - Logical or Scaling failure
- Solutions
  - Have a fallback service to call or at the very least a static response that allows the customer to carry on with their business
  - fail fast, and return to the fallback or wait to recover
  - (FIT) Fault Injection Testing
    - Synthetic Transactions
    - Override by device or account
    - % of live traffic up to 100% (test a launched service under load from live customers)
    - Enforced thoughout the call
  - How do we contrain testing scope?
    - the most critical services are identified as a group for barest functionality and a FIT reciepe is made and blacklists all non-essential services

#### Client Libraries

#### Data Persistence

- CAP Theorem: "In the presence of a network partition, you much choose between consistency and availability."
  - If you have 1 service needing to write to 3 databases, what if one write fails?
    - Do you cancel the write? or do you write to what you can?
    - you can aim for eventual consistency by writing to what databases you can and settle up later
    - The client writes to one node which then orchestrates the writing to all the other nodes
      - "Local Quorum"

#### Infrastructure

- Have redundant hosting across nodes to prevent catastrophic down time

### Scale

#### Stateless Services

- Its not a cache or database
- frequently accessed metadata
- no instance affinity
- loss of a node is a non-event
- Autoscaling groups
  - Compute efficiency
  - Node failure
  - Traffic Spikes
  - Performance Bugs
- Chaos monkey tool test that when a node dies, the service continues to work

#### Stateful Services

- databases and caches
- sometimes a custom app that holds large amounts of data (avoid storing business logic, and state within 1 application if you can avoid it)
- loss of a node is a notable event
- redundancy is fundemental
- EVCache -> difference nodes -> each node has multiple shard caches
- separate out systems used for batch versus real time transactions
- do request level caching
- have an encrypted token with the data to fall back on should the service be unavailable to updated the requested data

### Variance

#### Operation Drift

- drift over time
  - alert thresholds
  - timeouts, retries, fallbacks
  - throughput (RPS)
- Across microservices
  - Reliability best practices
- Continious learning and automation
  - Incident --> Resolution --> Review --> Remediation --> Analysis --> Best Practices? --> Automation --> Adoption
- Production Ready best practices
  - Alerts
  - Apache & tomcat
  - Automated canary Analysis
  - Autoscaling
  - Chaos
  - Consistent naming
  - ELB Config
  - Healthcheck
  - Immutable machine images
  - Squeeze testing
  - Staged, red/black deployments
  - Timeouts, retries, fallbacks

#### Polyglot & Containers

- The Paved Road (do this for a smooth experience)
  - Stash
  - Nebula/Gradle
  - BaseAMI/Ubuntu
  - Jenkins
  - Spinnaker
  - Runtime Platform
- Cost of Variance
  - Productivity Tooling
  - Insight & Triage Capabilities
  - Base Image Fragmentation
  - Node management
  - Library/Platform duplication
  - Learning curve - production expertise
- Strategic Stance
  - Raise awareness of costs
  - Constrain centralized support
  - Prioritize by impact
  - Seek reusable solutions

### Change

- Integrated, Automated practices
  - Conformity checks
  - Red/black pipelines
  - Automated canaries
  - Staged deployments
  - Squeeze tests
