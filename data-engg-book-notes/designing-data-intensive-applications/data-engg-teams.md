## Designing Data-Intensive Application

### Why read the book?
- To learn how to design data system that is reliable, scalable, and maintainable
- To understand different ways to set-up data system and be able to choose which is appropriate for the business requirement

I. Foundation of Data Systems

II. Distributed Data

III. Derived Data


## Foundation of Data Systems
### Chapter 1 Notes
- Types of data systems
  - databses, caches, search indexes, stream processing, batch processing
- Factors affecting design of a data system
  - skills and experience of people involved
  - legacy system dependencies
  - time scale for delivery
  - organization's tolerance of different kinds of risk
  - regulatory contraints

#### Reliability
- Tolerating fault is preferred unless in cases where prevention is better than cure (specifically when it comes to security cases concerns. This can't be undone)
- Hard disks are reported to have a mean time to failure (MTTF) of about 10 to 50 years. On a storage cluster with 10k disks, we should expect on average one disk to die per day
- Hardware Faults
  - Response
    - Add redundancy to individual hardware components
    - Disks may be set-up in a RAID configuration
    - Servers may have dual power supplies and hot-swappable CPUs
    - Datacenters may have batteries and diesel generators for backup power
- There is a move toward systems that can tolerate the loss of entire machines by using software fault-tolerance techniques in preference or in addition to hardware redundancy
- Software Error
  - Systematic error within the sytems
    - These often lie dormant for a long time until they are triggered by an unusual set of circumstances
  - Response
    - A system can provide some guarantee (ex. checking if the incoming message equals number of outgoing message), it can constantly check itself while it is running and raise an alert if a discrepancy is found
- Human Errors
  - Even when humans have the best intentions, humans are known to be unreliable
  - Response
    - Design systems taht minimizes opportunities for error. Ex. configuring on interface vs on api
    - Decouple place where people make mistakes
    - Test
    - Create quick recovery (Ex. rollback)
    - Monitoring (telemetry)
    - Good management and practices and training
- Importance of Reliability
  - in any system, a consequence with decreased reliability may occur
    - ex. 
      - Nuclear power station > Loss of life
      - Air traffic control > Accidents
      - business application > Lost productivity
      - Ecommerce > Lost Revenue/ Damaged reputation

#### Scalability
- Possible reasons
  - Load
    - ex. 10k users > 100k concurrent users
- Scalability is not a 1 dimensional label
- Describing Load
  - Load parameters
    - this depends on the architecture of your system
    - ex. requets per second to a web server, ratio of reads to writes in a db, no. of simultaenously active suers in a chat room, hit rate on a cache
- Performance
  - Assessed once we've already described what a load is in our system
  - 2 ways
    - Given an increased load parameter and same resources unchanged, how is the performance of the system affected?
    - Given increased load parameter, how much do we need to increase the resources if we want to keep performance unchanged?
  - Example of performance metrics:
    - Throughput
      - number of records we can process per second
      - total time it takes to run a job on a dataset
    - Response time
      - time between a client sending a request and receiving a response
  - Response time is not a single number, but as distribution of values
  - Usually, it's common to see average response time of a service reported. Instead of the average, let's use median (50th percentile/ p50) so that we can know that if a median response is 200ms, that means half of our requests return in less than 200 ms, and half of our requests take longer than that.
- Contracts
  - Service level objectives
  - Service level agreements
- 
## Reviewer Questions
1. How can you call an application data-intensive?
   - If data is its primary challenge - the quantity of data, the complexity of data, or the speed at which it is changing
2. What does reliability, scalability, and maintainability mean?
   - Reliability
     - Tolerating hardware and software faults, human error
   - Scalability
     - Measuring load and performance
     - Latency percentiles throughput
   - Maintainability
     - operability, simplicity, and evolvability
3. What is the difference of fault and failure?
    - A fault is defined as one component of the system deviatin from its spec
    - Failure is whne the system as a whole syops providing the required service to the user
4. What is the difference between latency and response time?
   - Response time is what the client sees: besisdes the actual time to process the request (service time)
   - Latency is the duration that a request is waiting to be handled (awaiting service)
5. What are tail latencies?
   1. High percentile of reponse times
  

## My questions:
1. What is CPU clock? What is a CPU Cycle> How does CPU cycle become a bottle neck?
2. Review how TCP works again
3. What is RAID?
    - RAID (redundant array of independent disks)
4. What are SLOs (service level objectives) and SLAs (service level agreements)?
5. What is head-of-line-blocking?
   - Small number of slow requests to hold up the processing of subsequent request