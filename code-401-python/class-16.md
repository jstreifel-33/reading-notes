# Serverless Functions

[Source: IBM Cloud Learn](https://www.ibm.com/cloud/learn/serverless)

## What is Serverless?

Serverless is a cloud computing model. It allows for automatic provisioning of computing resources and scaling of those resources based on demand.

Serverless computing offloads backend infrastructure to a cloud provider, allowing developers to focus on code instead of resource management.

There are still servers in "serverless" computing, but the customer doesn't have to worry about them at all. Combined with microservices and containers, serverless forms what is called **cloud-native** application development.

## Pros and Cons

Pros:

* Frees up time for developers to focus on front-end functionality and business logic
* Customers only pay for execution time, rather than a constant rent of machines.
* Support for any language
* Simplifies deploymnet and DevOps cycles
* Faster for certain workloads, such as parallel computing
* Provides system and user times, as well as info aggregation.

Cons:

* Does not offer savings for predictable or long-running processes. In these cases a traditional server may be more cost-effective
* Since serverless architecture can scale to zero, it often has a start-up latency if serving a request from zero.
* Monitoring and debugging a system while live can be difficult or impossible while utilizing serverless architecture.
* Transitioning to serverless architecture has the risk of locking a company into a provider. Transitioning away from serverless or to a new provider may not necessarily be easy to do.
