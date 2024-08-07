## Chapter 1: Data Warehousing, Business Intelligence, and Dimensional Modeling Primer

- From business needs we work backwards
- Appreciation to be 1/2 database administrator and 1/2 business analyst

## 2 Purpose of Data

1. to be used for operational record keeping
2. to be used for analyticsl decision making

### In Detail

1. Operational System

   1. data in
   2. one transaction at time
   3. optimized to process transactions quickly
   4. typically do not maintain history; reflects updated data
2. DW/BI System

   1. data out
   2. answers question that evaluate performance of a business (ex. this sales vs last week sales, which is higher)
   3. almost never deal with 1 transaction at a time
   4. optimized for high-performance queries
      1. high-performance: require hundred-millions of transactions to be searched and answered
   5. typically demand historical context

## Notes

- Converting pain points to business requirements

  - "We collect tons of data, but we can't access it" -> "DW/BI must make information easily accessible
  - "We spend entire meetings arguing about who has the righ numbers rather than making decisions" -> DW/BI system must present information consistently
- The data must be **intuitive and obvious** not just to the developer, but to the business user
- Data must be carefully assembled from a variety of sources, cleansed, quality assured, and released only when fit for user consumption
- Requirements for a DW/BI system

  - simple, intuitive, and obvious
    - simple enough for the end user to use this as decision support system
  - present data in
    - a consistently and clean (clean and validated)
    - timely way (ex. daily, weekly)
  - adapt to change
  - secure
  - user must use and accept system
    - if not used and embraced, you've failed the acceptance test
- IG Content Creator Metaphor (converted publisher metaphor to gen z terms)

  - Understand followers

    - Identify niche of demographic (analysts? marketer? promo bundling person?)
    - Find out what audience want in the IG feed (Determine decisions business users want to make with help of DW/BI system)
  - Ensure content appeals to the followers

    - Identify most liked/ hot content (tables with high read)
    - Upload high-quality content, but still with consistent presentation style/branding
  - Sustain follower count

    - Upload content on a regular basis (Update DW/BI system on a regular basis)
- Same with IG Content Creators, DW/BI managers must publish data that has been collected form a variety of sources and edited for quality and consistency

## Dimensional modeling Introduction

- Dimensional modeling
  - deliver data that's understandable to the business users
  - deliver fast query performance

[![The Rise and Fall of the OLAP Cube](https://www.holistics.io/blog/content/images/2020/01/olap-3d-cube.png)](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.holistics.io%2Fblog%2Fthe-rise-and-fall-of-the-olap-cube%2F&psig=AOvVaw1_WnJvqaiDy2rn377QoLAx&ust=1723131650931000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCNjtvuGb44cDFQAAAAAdAAAAABAR)

- Edge of a cube: product, market (geography), time
- Points/smaller cube inside cube: sales volume or profit
- 3NF models: normalized models
- 3NF structures: useful in operational processing
- Users can't understand/remember 3NF models that resembles a map of the Los Angeles freeway system

page 44 - 71

Star Schemas VS OLAP Cubes

## Summary

1. What are the goals of having DW/BI system?
2.
