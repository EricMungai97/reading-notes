# Serverless Functions

[source](https://www.redhat.com/en/topics/cloud-native-apps/what-is-serverless)

[Source](https://www.ibm.com/cloud/learn/serverless)

`Serverless function` is a cloud-native development model that allows developers to build and run applications without having to manage servers. There are still servers in serverless, but they are abstracted away from app development.



`Function-as-a-service` is a cloud computing service that enables developers to run code or containers in response to specific events or requests, without specifying or managing the infrastructure required to run to code.

`Serverless` is an entire stack of services that can respond to specific events or requests, and scale to zero when no longer in use

**Serverless Vs Platform as a service(Paas), containers and VMs**

`Provisioning time` - Measured in milliseconds for serverless, vs. minutes to hours for the other models.

`Maintenance`-  None for serverless, compared to a continuum from light to medium to heavy for PaaS, containers and VMs respectively.

`Scaling`- Auto-scaling—including auto-scaling to zero—is instant and inherent for serverless. The other models offer automatic but slow scaling that requires careful tuning of auto-scaling rules, and no scaling to zero.

`Capcity planning` -  None needed for serverless. The other models require a mix of some automatic scalability and some capacity planning.

`Statelessness`- : Inherent for serverless, which means scalability is never a problem; state is maintained in an external service or resource. PaaS, containers and VMs can leverage HTTP, keep an open socket or connection for long periods of time, and store state in memory between calls.

`High availability`
`Resource utilization`- Serverless is 100% efficient because there are no such things thing as idle capacity—it is invoked only upon request. All other models feature at least some degree of idle capacity.

***Pros and Cons of serverless***

1. Improved developer productivity.

2. Pay for execution only. The meter starts when the request is made and ends when the execution finishes.

3. Develop in any language. Serverless is a polygot environment, enabling developers to code in any language or framework.

4. Streamlined development/DevOps cycles. since developers don't spend time defining infrastructure required to integrate, test, deliver and deploy code builds into production.

5. Cost-effective performance. 

6. Usage visibility. Serverless platforms provide near-total visibility into system and user times and can aggregate usage information

The most common use case of serverless today is supporting `microservices architectures`.