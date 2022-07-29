# Chapter 1: Reliable, Scalable, and Maintainable Applications

## Examples of functionalities needed by a *data-intensive* application
1. store data to retrieve find it later- **databases**
2. remember the result of an expensive operation, to speed up reads - **caches**
3. allow users to search data by keyword - **search indexes**
4. send a message to another process to be handled asynchronously - **stream processing**
5. periodically crunch a large amount of accumulated data - **batch processing**

## Example of tools that do not exactly fit a single traditional category
1. Redis - a datastore that's also used for message queues
2. Apache Kafka - a message queue with database-like durability

## 3 main concerns that are important in software systems
1. Reliability
  - System should continue to work correctly even in the face of adversity
2. Scalability
  - As system grows, there should be reasonable ways of dealing with that growth
3. Maintainability
   - Over time, many different people will work on the system both maintaining current behavior and adapting the system to new use cases. They should all be able to work on it productively

## Reliability
- To build a fault-tolerant system, it would make sense to increase rate of faults by triggering them deliberately (ex. Netflix Chaos Monkey)

  1. Hardware faults
   - Hard disks are reported as having a mean time to failure (MTTF) of about 10 to 50 years. Thus, on a storage cluster with 10,000 disks, we should expect on average one disk to die per day
  2. Sofware Errors
    - Systematic error
      - ex. A software bug that causes every instance of an application server to crash when given a particular bad input. For example, consider the leap second on June 30, 2012, that caused many applications to hang simultaneously due to a bug in the Linux kernel
  3. Human Errors
      - How to make systems reliable in spite of *unreliable* humans
        - Design system in a way that minimizes opportunities for error
        - Separate sandbox environment from prod
        - Test thouroughly. Automated if possible.
        - Allow quick and easy recovery from human error such as rollbacks
        - Setting up detailed and clear monitoring, such as performance metrics and error rates
        - Implement good management practice and training