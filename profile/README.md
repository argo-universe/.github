<img src="https://cncf-branding.netlify.app/img/projects/argo/horizontal/color/argo-horizontal-color.png" height="100" alt="" />

# What is Argo Universe?

The Argo Universe is a well-designed design pattern and an all-encompassing Kubernetes resource boilerplate comprising several repositories. Our foremost objective is to leverage our expertise and knowledge to benefit the community by furnishing a Kubernetes stack demonstration exclusively using ArgoCD. This exemplifies a sample GitOps methodology that incorporates all the essential components in a streamlined, user-friendly manner.

>Design patterns are reusable solutions and best practices for designing, building, and managing platform systems. They provide a common language and approach for solving common problems in platform development and management, such as architectural patterns, deployment patterns, scaling patterns, and operational patterns. By using design patterns, platform teams can benefit from proven solutions and best practices, leading to more efficient and reliable development and management of platform systems.

    
We have developed a collection of repositories, known as Argo Universe, to serve as a starting point for individuals interested in GitOps, ArgoCD, or Kubernetes. It features an ArgoCD boilerplate that can be utilized as a reference or launchpad.

Furthermore, we have supplementary repositories that store example app and application configurations. These repositories offer a sample workflow for constructing and deploying an application.

``` mermaid
flowchart  LR
subgraph Repositories
    abb(argo-bigbang) 
    acnf(app-config) 
    backend(backend)
    frontend(frontend)
end

```

## Getting Started
 
### Cloud Resources

Given the fact that the cloud resource requirements are highly dependent on the complexity of the user's stack, the number of resources required, and the associated costs, we recognize the need to provide meticulous guidance on managing the Argo Universe. This stage is dedicated to offering the essential steps for installing and configuring the Argo Universe in either a local environment or an already provisioned platform accessible to the user. Our overarching aim is to facilitate a seamless installation experience for our users while ensuring they have access to the appropriate resources necessary for their specific needs.


### Kubernetes Stack

To get started with Argo Universe, simply check out our [Argo Bigbang repo](https://github.com/argo-universe/argo-bigbang). Feel free to explore and use the repositories as you see fit.


``` mermaid
flowchart  LR
 client([client])---->ingress[Ingress];
 ingress--> service1[Service];
 ingress--> service2[Service];
 subgraph k8s ["Kubernetes Cluster"]
    ingress;
    subgraph applications
        service1-->pod1[frontend];
        service2-->pod2[backend];
    end
    subgraph cluster-addons
        
        Vault;
        ArgoCD(ArgoCD);
        ING(Ingress Contrller)
        CM(Certificate Manager);
        SI(Secrets Injection Manager);

    end
 end



 classDef plain fill:#ddd,stroke:#fff,stroke-width:4px,color:#000;
 classDef k8sAddons fill:#28d128,stroke:#128a12,stroke-width:2px,color:#fff;
 classDef whiteBack fill:#fff,stroke:#128a12,stroke-width:1px,color:#000;
 classDef k8s fill:#326ce5,stroke:#fff,stroke-width:4px,color:#fff; 
 class ingress,service1,service2,pod1,pod2 k8s;
 class cluster-addons,applications whiteBack;
 class ArgoCD,CM,SI,ING k8sAddons;
 class client plain;



```
### Cluster Addons

Kubernetes cluster add-ons are additional components that can be installed on top of a Kubernetes cluster to extend its functionality and provide additional features. These add-ons can help with tasks such as monitoring, logging, networking, and security.

##### ArgoCD
ArgoCD is a continuous delivery tool that automates the deployment of applications to Kubernetes clusters. It is used in Kubernetes to streamline the deployment process by providing a unified interface for managing deployment configurations and deployment targets.

#### Ingress  
Nginx ingress controller is a Kubernetes-native solution for managing incoming traffic to a cluster. It is used in Kubernetes to route incoming traffic to the appropriate application and to provide load balancing and SSL termination.

##### Secret Manager 
External secret store is a Kubernetes tool that allows for the management of secrets in an external, secure location outside of Kubernetes. It is used in Kubernetes to improve security by separating secret management from the main cluster and providing access control and auditing capabilities.

##### Certificate Manager 
Cert manager is a Kubernetes tool for automatically managing SSL/TLS certificates for Kubernetes workloads. It is used in Kubernetes to simplify the process of managing certificates and to ensure that workloads are always securely encrypted.

## Contributing

We welcome contributions from anyone who is interested in GitOps, ArgoCD, or Kubernetes. You can contribute to Argo Universe by submitting pull requests, opening issues, or sharing your thoughts and ideas.

We believe that by collaborating with others, we can improve and expand our knowledge and share it with the world. Please take a look at the [Contribution Guidelines](/CONTRIBUTING.md).

## License

Argo Universe is released under the [Apache License 2.0](LICENSE.md). 

--- 
