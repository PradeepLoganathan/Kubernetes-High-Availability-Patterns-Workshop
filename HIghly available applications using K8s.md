# Highly available microservices using Kubernetes

## Nines

| Availability %                      | Downtime per   year | Downtime per   quarter | Downtime per   month | Downtime per week | Downtime per day   (24 hours) |
|-------------------------------------|---------------------|------------------------|----------------------|-------------------|-------------------------------|
| 99% ("two nines")                   | 3.65 days           | 21.9 hours             | 7.31 hours           | 1.68 hours        | 14.40 minutes                 |
| 99.9% ("three nines")             | 8.77 hours          | 2.19 hours             | 43.83 minutes        | 10.08 minutes     | 1.44 minutes                  |
| 99.95% ("three and a half nines") | 4.38 hours          | 65.7 minutes           | 21.92 minutes        | 5.04 minutes      | 43.20 seconds                 |
| 99.99% ("four   nines")             | 52.60 minutes       | 13.15 minutes          | 4.38 minutes         | 1.01 minutes      | 8.64 seconds                  |

## Definitions

* Recovery Time Objective (RTO)
* Recovery Point Objective (RPO)

### Recovery Time Objective


### Recovery Point Objective


## Scalability Considerations

Scalability is a key factor in providing a consistent, high performance end user experience.
A microservice is composed of multiple layers. Each layer should have the necessary ability to scale independently of others.

|Layer                                  |Impact             |Ability|
|-----|------|-------|
|Application|Microservice architecture| The microservice should have the ability to scale horizontally. The microservice should be able to be scaled by provisioning additional pods and replicas.|
|Cluster| Kubernetes cluster design | The cluster provides the ability to scale pods, nodes ( node sizes and number of nodes)|
|Infrastrcuture| SDDC ? HCI ?, VSphere ? | The infrastrcture should provide the ability scale the number of nodes up and down. It should also provide the ability to scale the size of the nodes ( VCPU, VCore ?)

### Application design requirements

#### Shared nothing architecture

A single pod in a cluster can satisfy a request independently. The pod should not need to coordinate with other pods. Shared nothing architecture eliminates single points of failure. If indvidual pods fail other pods operate without any repurcussions.Shared nothing architecture enables scalability, perforamance and fault tolerance.

### Cluster design requirements

#### System node and Application node isolation

1. Nodes running kubernetes systems proceses should be isolated from nodes running application workloads.
2. This can be achieved by using labels.

#### Use Policy to enforce constraints

Cluster policies can be used to enforce pod requirements as necessary.

#### Use proximate container registries


### Infrastrcuture design requirements

[](https://docs.vmware.com/en/VMware-Validated-Design/5.1/sddc-architecture-and-design/images/GUID-96FEDB80-2849-4358-B9DD-0A83F7B13D71-high.png)
