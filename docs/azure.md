# Microsoft Azure
- [Azure](#azure)
- [Microsoft Linux Distribution CBL Mariner](#microsoft-linux-distribution-cbl-mariner)
- [ARM Templates](#arm-templates)
- [Azure DevOps](#azure-devops)
- [Secure DevOps Kit for Azure](#secure-devops-kit-for-azure)
- [Mobile Apps](#mobile-apps)
- [Powershell](#powershell)
    - [Powershell repos](#powershell-repos)
- [IaC with PowerShell DSC Desired State Configuration](#iac-with-powershell-dsc-desired-state-configuration)
- [Azure Bicep](#azure-bicep)
- [AKS Azure Kubernetes Service](#aks-azure-kubernetes-service)
- [Azure Red Hat OpenShift ARO](#azure-red-hat-openshift-aro)
- [Azure Traffic Manager](#azure-traffic-manager)
- [Azure OpenVPN](#azure-openvpn)
- [Azure Security](#azure-security)
- [WinGet Windows Package Manager CLI](#winget-windows-package-manager-cli)
- [Windows 11](#windows-11)
- [ASP.NET Core](#aspnet-core)

## Azure
- [Microsoft Azure](https://azure.microsoft.com/)
- [Microsoft Docs](https://docs.microsoft.com/)
- [Azure Docs](https://docs.microsoft.com/azure)
- [Introducing the third of three Microsoft Clouds: Azure](https://www.catapultsystems.com/blogs/introducing-the-third-of-three-microsoft-clouds-azure/). 4 major sections of the Cloud Models are: 
    - On-Premises: As you start on the left in the traditional on-prem configuration you are responsible for all layers of IT from the networking stack all the way up to the applications which are being provided. You may also be responsible for the data center, power, Internet service, and other underlying aspects.
    - Infrastructure as a Service: In IaaS (Take & Bake) the cloud vendor is responsible for the stack from networking through virtualization and your IT team is responsible for the Operating System (OS) through the applications. Common uses of IaaS are testing environments, development environments or hosting of a website.
    - Platform as a Service: In PaaS (Pizza Delivered) the cloud vendor is responsible for the networking layers through the runtime layer and your IT team is responsible for the data and the applications. PaaS is commonly used to test, build and deploy applications for an organization.
    - Software as a Service: In SaaS (Dining Out) the cloud vendor is responsible for all layers from the networking through to the application layer. A common example of SaaS is a web-based email service such as Outlook, Hotmail or Gmail.
- [medium: Scaling Applications in the Cloud](https://medium.com/faun/scaling-applications-in-the-cloud-52bb6dfbac4e)
- [thenewstack.io: Azure Kubernetes Service Replaces Docker with containerd](https://thenewstack.io/azure-kubernetes-service-replaces-docker-with-containerd/)
- [blog.sixeyed.com: You can't always have Kubernetes: running containers in Azure VM Scale Sets](https://blog.sixeyed.com/you-cant-always-have-kubernetes-running-containers-in-azure-vm-scale-sets/)
- [devblogs.microsoft.com: Deploy Spring Boot applications by leveraging enterprise best practices – Azure Spring Cloud Reference Architecture](https://devblogs.microsoft.com/java/deploy-spring-boot-applications-by-leveraging-enterprise-best-practices/)
- [Azure Key Vault to Kubernetes](https://github.com/SparebankenVest/azure-key-vault-to-kubernetes) Azure Key Vault to Kubernetes (akv2k8s for short) makes it simple and secure to use Azure Key Vault secrets, keys and certificates in Kubernetes.
- [techcommunity.microsoft.com: Non-interactive logins: minimizing the blind spot](https://techcommunity.microsoft.com/t5/azure-sentinel/non-interactive-logins-minimizing-the-blind-spot/ba-p/2287932) In this blog post, we will review the new Azure Sentinel data streams for Azure Active Directory non-interactive, service principal, and managed identity logins. We will also share the new security content we built and updated in the product, which includes analytics rules for the detection part and workbooks to assist our customers to deal with this blind spot.
- [returngis.net: Replicación de blobs entre dos cuentas de Azure Storage en dos tenants diferentes](https://www.returngis.net/2021/06/replicacion-de-blobs-entre-dos-cuentas-de-azure-storage-en-dos-tenants-diferentes/)
- [c-sharpcorner.com: Comparing AWS SQL Server With Azure SQL Database](https://www.c-sharpcorner.com/article/comparing-aws-sql-server-with-azure-sql-database/)
- [techcommunity.microsoft.com: How to create a VPN between Azure and AWS using only managed solutions](https://techcommunity.microsoft.com/t5/fasttrack-for-azure/how-to-create-a-vpn-between-azure-and-aws-using-only-managed/ba-p/2281900)
- [teacdmin.net: How To Enable Multiple RDP Sessions on Windows Server](https://tecadmin.net/how-to-enable-multiple-rdp-sessions-on-windows-server/)
- [Neoteroi/essentials-configuration-keyvault](https://github.com/Neoteroi/essentials-configuration-keyvault) Azure Key Vault source for essentials-configuration

## Microsoft Linux Distribution CBL Mariner
- [thenewstack.io: Deploying Microsoft’s New Linux Distribution as a VM is Not Easy](https://thenewstack.io/deploying-microsofts-new-linux-distribution-as-a-vm-is-not-easy/)
- [github.com/microsoft/CBL-Mariner](https://github.com/microsoft/CBL-Mariner) Linux OS for Azure 1P services and edge appliances

## ARM Templates
- [thomasmaurer.ch: Learn how to deploy and manage Azure resources with ARM templates](https://www.thomasmaurer.ch/2020/12/learn-how-to-deploy-and-manage-azure-resources-with-arm-templates/)
- [techcommunity.microsoft.com: ARM Template Specs now GA!](https://techcommunity.microsoft.com/t5/azure-governance-and-management/arm-template-specs-now-ga/ba-p/2402618)
- [docs.microsoft.com: Azure Resource Manager template specs](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-specs)

## Azure DevOps
- [Azure DevOps 🌟](https://azure.microsoft.com/services/devops/)
- [Azure DevOps Labs 🌟](https://www.azuredevopslabs.com/)
- [info.acloud.guru: Deploying your first kubernetes app with Azure DevOps](https://info.acloud.guru/resources/deploy-kubernetes-app-with-azure-devops)
- [info.acloud.guru: Azure DevOps VS GitHub: Comparing Microsoft's DevOps Twins](https://info.acloud.guru/resources/azure-devops-vs-github-comparing-microsofts-devops-twins)
- [techcommunity.microsoft.com: Building a path to success for microservices and .NET Core - Project Tye + GitHub Actions](https://techcommunity.microsoft.com/t5/apps-on-azure/building-a-path-to-success-for-microservices-and-net-core/ba-p/1502270)
- [medium: Azure DevOps HandBook !](https://medium.com/@arunksingh16/azure-devops-handbook-d6dcd82da1b7)
- [Azure DevOps Tips: “Each” Loops](https://medium.com/@therealjordanlee/azure-devops-tips-each-loops-c082c692d025)
- [cloudskills.io: Getting Started with Git and Azure DevOps: The Ultimate Guide 🌟](https://cloudskills.io/blog/git-azure-devops)
- [zartis.com: Simplify Your SDLC with Azure DevOps](https://www.zartis.com/simplify-your-sdlc-with-azure-devops/)
- [azurebrains.com: Despliega tu Azure Function App con Terraform y Azure DevOps 🌟](https://www.azurebrains.com/2021/03/25/despliega-azure-function-terraform-azuredevops/)
- [devblogs.microsoft.com: Controlling Release Pipelines with Gates and Azure Policy Compliance 🌟](https://devblogs.microsoft.com/devops/controlling-release-pipelines-with-gates-and-azure-policy-compliance/)
- [youtube: Azure DevOps Pipeline and Image Builder](https://www.youtube.com/watch?v=zL0eLEl2BxI&ab_channel=TravisRoberts)
- [dev.to: Setting up a CI-CD Pipeline Using Azure DevOps 🌟](https://dev.to/gbengelebs/setting-up-a-ci-cd-pipeline-using-azure-devops-4gb)
- [zartis.com: Simplify Your SDLC with Azure DevOps 🌟](https://www.zartis.com/simplify-your-sdlc-with-azure-devops/)
- [thomasthornton.cloud: Scout Suite reports using Azure DevOps Pipeline](https://thomasthornton.cloud/2021/04/29/scout-suite-reports-using-azure-devops-pipeline/) Interesting article on how to fecth az DevOps pipelines reports as a static website
- [Azure DevOps Dashboard](https://github.com/cschotte/Azure-DevOps-Dashboard) 
- [cloud.google.com: Crea una canalización de CI/CD con Azure Pipelines y Compute Engine](https://cloud.google.com/architecture/creating-cicd-pipeline-vsts-compute-engine)
- [letsdevops.net: Introduction to Azure DevOps for Beginners - Create CI/CD Pipelines, Setup Repository 🌟](https://www.letsdevops.net/post/letsdevops-introduction-to-azure-devops-for-beginners)

## Secure DevOps Kit for Azure
- [Secure DevOps Kit for Azure](https://github.com/azsk/DevOpsKit)
- [DevOpsKit-docs](https://github.com/azsk/DevOpsKit-docs)
- [ismiletechnologies.com: Secure DevOps Kit For Azure(AzSK)](https://www.ismiletechnologies.com/devsecops/secure-devops-kit-azureazsk/)

## Mobile Apps
- [Visual Studio App Center VS Azure Pipelines](https://docs.microsoft.com/en-us/appcenter/build/choose-between-services)
- [itnext.io: How to setup CI CD pipelines for Android with Azure DevOps](https://itnext.io/how-to-setup-ci-cd-pipelines-for-android-with-azure-devops-2a4ded0de0e7) At Royale Cheese initially we had setup CI/CD for Android via Microsoft’s Visual Studio App Center (an upgrade of Hockey App), but last year they declared the retirement of MBaas which got us worried about the overall future of VS App Center. That was one of the reasons we wanted to switch away from it. Secondly, the free tier provided around 400 minutes of build time per month per account which would had been sufficient for other technologies, but Android takes around 15 minutes to create a single build and deploy. We all know what gradle is capable of 😉. So having multiple apps (both iOS and Android) in the same account didn’t fare well.
- [arjavdave.com: Continuous Integration: CI/CD for iOS (Part 1)](https://arjavdave.com/2021/03/11/continuous-integration-for-ios-on-azure-devops-part-1/)
- [sahansera.dev: Multi-stage builds for Ionic Apps with Azure Pipeline Templates](https://sahansera.dev/multi-stage-builds-with-azure-pipelines-ionic/)
- [sahansera.dev: Publishing Android Apps to Microsoft App Center from Azure DevOps](https://sahansera.dev/publishing-android-apps-to-microsoft-appcenter/)
- [yoshevski.medium.com: Cost-effective Azure Devops and AppCenter integration](https://yoshevski.medium.com/cost-effective-azuredevops-and-appcenter-integration-fe606725d5d5)
- [youtube: Signing & Versioning iOS & Android Apps | DevOps for Mobile](https://www.youtube.com/watch?v=s1grtSSIRVA&ab_channel=dotNET)

## Powershell
- [PowerShell](https://docs.microsoft.com/powershell/)
- [PowerShell Gallery](https://www.powershellgallery.com/) The central repository for sharing and acquiring PowerShell code including PowerShell modules, scripts, and DSC resources.
- [PowerShell Community](https://devblogs.microsoft.com/powershell-community/)
- [reddit.com: PowerShell Core yaml support?](https://www.reddit.com/r/PowerShell/comments/flzsx5/powershell_core_yaml_support/)
- [powershellmagazine.com](https://powershellmagazine.com/)
- [dbatools.io](https://dbatools.io/) SQL Server instance migrations and best practice implementation.
- [thomasmaurer.ch: PowerShell: Download script or file from GitHub](https://www.thomasmaurer.ch/2021/07/powershell-download-script-or-file-from-github/)

### Powershell repos
- [Abhisheksinhacoder/collection-of-useful-scripts](https://github.com/Abhisheksinhacoder/collection-of-useful-scripts)
- [jrussellfreelance/powershell-scripts](https://github.com/jrussellfreelance/powershell-scripts)
- [github.com/search?l=powershell](https://github.com/search?l=powershell&q=stars%3A%3E1&s=stars&type=Repositories)

## IaC with PowerShell DSC Desired State Configuration
- [docs.microsoft.com: Desired State Configuration overview for decision makers 🌟](https://docs.microsoft.com/en-us/powershell/scripting/dsc/)
- [docs.microsoft.com: Using configuration data in DSC](https://docs.microsoft.com/en-us/powershell/scripting/dsc/configurations/configData)
- [octopus.com: Getting started with PowerShell Desired State Configuration (DSC)](https://octopus.com/blog/getting-started-with-powershell-dsc) PowerShell DSC is an Infrastructure as Code (IaC) technology that uses PowerShell to create Managed Object Format (MOF) files, which Windows Management Instrumentation (WMI) can use to configure a machine. In other words, PowerShell DSC uses PowerShell to programmatically configure your Windows-based computers. Additionally, DSC can monitor the state of the configured resources to make sure your machines stay consistent. Along with monitoring, DSC can also automatically correct the configuration of your system, so it’s always in the desired state. **PowerShell != PowerShell DSC**

## Azure Bicep
- [Bicep](https://github.com/Azure/bicep) Bicep is a Domain Specific Language (DSL) for deploying Azure resources declaratively. 

## AKS Azure Kubernetes Service 
- [docs.microsoft.com: Microservices architecture on Azure Kubernetes Service (AKS) 🌟](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks-microservices/aks-microservices) This reference architecture shows a microservices application deployed to Azure Kubernetes Service (AKS). It describes a basic AKS configuration that can be the starting point for most deployments. The architecture consists of the following components:
    - Azure Kubernetes Service (AKS)
    - Kubernetes cluster
    - Virtual network
    - Ingress
    - Azure Load Balancer
    - External data stores
    - Azure Active Directory
    - Azure Container Registry
    - Azure Pipelines
    - Helm
    - Azure Monitor
- [trstringer.com: Run Kubernetes Pods on Specific VM Types in AKS](https://trstringer.com/run-kubernetes-pods-on-vm-types/)
- [docs.microsoft.com: AKS-managed Azure Active Directory integration](https://docs.microsoft.com/en-us/azure/aks/managed-aad)
- [build5nines.com: Terraform: Create an AKS Cluster 🌟](https://build5nines.com/terraform-create-an-aks-cluster/)
- [github.com: AKS: Use AAD identity for pods and make your SecOps happy](https://github.com/dfrappart/articles/blob/master/podidentityjourney.md)
- [docs.microsoft.com: Microservices architecture on Azure Kubernetes Service (AKS) 🌟](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks-microservices/aks-microservices)
- [techcommunity.microsoft.com: Containerize and migrate applications to AKS with the Azure Migrate’s new App Containerization tool](https://techcommunity.microsoft.com/t5/azure-migration/containerize-and-migrate-applications-to-aks-with-the-azure/ba-p/2178551)
- [mehmetozkaya.medium.com: Deploying .Net Microservices to Azure Kubernetes Services(AKS) and Automating with Azure DevOps](https://mehmetozkaya.medium.com/deploying-net-microservices-to-azure-kubernetes-services-aks-and-automating-with-azure-devops-c50bdd51b702)
- [faun.pub: How to implement Azure Kubernetes Service (AKS) in Cloud?](https://faun.pub/azure-kubernetes-service-aks-d1e71c7ecbe6)
- [adamrushuk.github.io: Increasing the volumeClaimTemplates Disk Size in a Statefulset on AKS](https://adamrushuk.github.io/increasing-the-volumeclaimtemplates-disk-size-in-a-statefulset-on-aks/)
- [nillsf.com: Running Windows containers on the Azure Kubernetes Service (AKS)](https://nillsf.com/index.php/2020/11/17/running-windows-containers-on-the-azure-kubernetes-service-aks)
- [itnext.io: Running Your Microservices Securely on AKS](https://itnext.io/running-your-microservices-securely-on-aks-417a110b2e76)
- [docs.microsoft.com: Create an HTTPS ingress controller on Azure Kubernetes Service (AKS)](https://docs.microsoft.com/en-us/azure/aks/ingress-tls)
- [blog.nillsf.com: Customize core dump in Azure Kubernetes](https://blog.nillsf.com/index.php/2020/12/06/customize-core-dump-in-azure-kubernetes/)
- [medium: Secure your Microservices on AKS — Part 1 🌟](https://itnext.io/running-your-microservices-securely-on-aks-417a110b2e76)
    - [medium: Secure your Microservices on AKS — Part 2 🌟](https://medium.com/microsoftazure/secure-your-microservices-on-aks-part-2-5496bf2ba00c)
- [zartis.com: How To Save A Fortune On Azure Kubernetes Service](https://www.zartis.com/minimizing-costs-aks/)
- [itnext.io: AKS Performance: Limit Ranges](https://itnext.io/aks-performance-limit-ranges-8e18cbebe351) Limit Ranges can be used to fine tune your resource consumption by limiting your min/max requests/limits in namespaces.
- [devoteam.com: Azure Kubernetes Service (AKS) with Azure DevOps](https://nl.devoteam.com/en/blog-post/azure-kubernetes-service-aks-with-azure-devops/)
- [itnext.io: Kubernetes Ingress on Azure using the Application Gateway](https://itnext.io/kubernetes-ingress-on-azure-using-the-application-gateway-2779b647deb5) How to expose multiple services on a single host
- [joachim8675309.medium.com: AKS with GRPC and ingress-nginx](https://joachim8675309.medium.com/aks-with-grpc-and-ingress-nginx-32481a792a1) Using GRPC with ingress-nginx add-on with AKS
- [thenewstack.io: Microsoft’s Practical Approach to Kubernetes Management](https://thenewstack.io/microsoft-takes-practical-approach-to-kubernetes-management/)
- [medium: AKS with Calico Network Policies](https://medium.com/geekculture/aks-with-calico-network-policies-8cdfa996e6bb) Using Calico Network Policy with Azure Kubernetes Server
- [itnext.io: Network Isolated AKS — Part 1: Controlling network traffic](https://itnext.io/network-isolated-aks-part-1-controlling-network-traffic-2cd0e045352d)
- [thenewstack.io: Turbocharging AKS Networking with Calico eBPF](https://thenewstack.io/turbocharging-aks-networking-with-calico-ebpf/)
- [carlos.mendible.com: AKS: Persistent Volume Claim with an Azure File Storage protected with a Private Endpoint](https://carlos.mendible.com/2021/08/02/aks-persistent-volume-claim-with-an-azure-file-storage-protected-with-a-private-endpoint/)
- [joachim8675309.medium.com: AKS with Istio Service Mesh](https://joachim8675309.medium.com/istio-service-mesh-on-aks-1b6ed16f6890) Securing traffic with Istio service mesh on AKS
- [optisolbusiness.com: Implementing Microservices Architecture in AKS](https://www.optisolbusiness.com/insight/implementing-microservices-architecture-in-aks)
- [blog.kasten.io: AKS and Storage: How to Design Storage for Cloud Native Applications](https://blog.kasten.io/aks-and-storage-how-to-design-storage-for-cloud-native-applications)
- [blog.kasten.io: AKS and Storage: Performance Differences Among K8s Storage Services](https://blog.kasten.io/aks-and-storage-performance-differences-among-kubernetes-storage-services)

## Azure Red Hat OpenShift ARO
- [ARO](https://www.openshift.com/products/azure-openshift)
- [aroworkshop.io 🌟](http://aroworkshop.io/) 

## Azure Traffic Manager
- [Azure Traffic Manager](https://docs.microsoft.com/azure/traffic-manager/)

## Azure OpenVPN
- [Create an Azure Active Directory tenant for P2S OpenVPN protocol connections](https://docs.microsoft.com/azure/vpn-gateway/openvpn-azure-ad-tenant)

## Azure Security
- [techcommunity.microsoft.com: Security Control: Implement security best practices](https://techcommunity.microsoft.com/t5/azure-security-center/security-control-implement-security-best-practices/ba-p/2269914)

## WinGet Windows Package Manager CLI
- [WinGet: Welcome to the Windows Package Manager Client (aka winget.exe) repository](https://github.com/microsoft/winget-cli/) Windows Package Manager CLI (aka winget)
- [muycomputer.com: WinGet 1.0, ya está aquí el administrador de paquetes para Windows](https://www.muycomputer.com/2021/06/03/winget-1-0-paquetes-windows-10/)
- [thomasmaurer.ch: Getting started with Windows Package Manager WinGet](https://www.thomasmaurer.ch/2021/07/getting-started-with-windows-package-manager-winget/)

## Windows 11
- [thenewstack.io: This Week in Programming: Windows Opens Up to Android Developers](https://thenewstack.io/this-week-in-programming-windows-opens-up-to-android-developers/)

## ASP.NET Core
- [blog.jetbrains.com: Getting Started with ASP.NET Core and gRPC](https://blog.jetbrains.com/dotnet/2021/07/19/getting-started-with-asp-net-core-and-grpc/)
- [dzone: Building a RESTful Service Using ASP.NET Core and dotConnect for PostgreSQL](https://dzone.com/articles/building-a-restful-service-using-aspnet-core-and-d) This article looks at RESTful architecture and how we can implement a RESTful service using ASP.NET Core and dotConnect for PostgreSQL.

<center>
[![pizza model](images/pizza-model-vert.jpeg)](https://www.catapultsystems.com/blogs/introducing-the-third-of-three-microsoft-clouds-azure/)
</center>