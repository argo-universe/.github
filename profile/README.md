# Argo Universe
<img src="https://cncf-branding.netlify.app/img/projects/argo/horizontal/color/argo-horizontal-color.png" height="100" alt="" />

Argo Universe is a comprehensive Kubernetes resource boilerplate consisting of multiple repositories. Our primary goal is to share our expertise and experience with the community by providing a Kubernetes stack example using only ArgoCD. This is a sample GitOps methodology that offers all the necessary components in a few simple steps.

We have developed a collection of repositories, known as Argo Universe, to serve as a starting point for individuals interested in GitOps, ArgoCD, or Kubernetes. It features an ArgoCD boilerplate that can be utilized as a reference or launchpad.

Furthermore, we have supplementary repositories that store example app and application configurations. These repositories offer a sample workflow for constructing and deploying an application.

# Taka a look at  LIVE ArgoCD installation from here https://argocd.argouniverse.com/


## Getting Started

To get started with Argo Universe, simply check out our [Argo Bigbang repo](https://github.com/argo-universe/argo-bigbang). Feel free to explore and use the repositories as you see fit.


``` mermaid
flowchart  TB
subgraph repository [GitHub]
    APPCONF(App config) 
    BIGBANG(Argo Bigbang) 
    SAPP(Sample App)

    subgraph Pipeline [Pipeline]
        BUILD[Build the image] 
        UPDATEIMAGE[Update Image tag] 
    end


end

subgraph kubernetes [Kubernetes]
        AROGO(ArgoCD) 
        SA(Sample App)
        ING(Ingress)
        CERT(Cert Manager)
        EXT(External Secret)
end


AROGO ----->  APPCONF
AROGO ---->  BIGBANG 
AROGO -->  ING
AROGO --> CERT
AROGO -->  EXT 
AROGO -->  SA
SAPP --> |commit or tag <br> starts the pipeline| Pipeline
BUILD --> UPDATEIMAGE
BUILD --> DockerHub
UPDATEIMAGE --> APPCONF

kubernetes ------ DockerHub

linkStyle 0 stroke-width:2px,fill:none,stroke:blue;
linkStyle 5 stroke-width:2px,fill:none,stroke:blue;
linkStyle default stroke-width:2px,fill:none,stroke:red;
```
## Installation

Clone the  [Argo Bigbang](https://github.com/argo-universe/argo-bigbang) run install.sh file with environment name

```bash

$ git clone https://github.com/argo-universe/argo-bigbang.git
$ cd argo-bigbang 
# this will install argocd and bigbang app then bigbang app will install  cluster addons and sample app
$ ./install.sh dev
```


## Contributing

We welcome contributions from anyone who is interested in GitOps, ArgoCD, or Kubernetes. You can contribute to Argo Universe by submitting pull requests, opening issues, or sharing your thoughts and ideas.

We believe that by collaborating with others, we can improve and expand our knowledge and share it with the world.

## License

Argo Universe is released under the [Apache License 2.0](LICENSE.md). 

--- 
