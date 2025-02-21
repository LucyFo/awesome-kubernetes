# API Marketplaces. API Management with API Gateways & Developer Portals 
- [Introduction](#introduction)
- [API Landscape and API Marketplaces](#api-landscape-and-api-marketplaces)
	- [API Marketplaces](#api-marketplaces)
	- [Rapid API Marketplace. Free Public & Open REST APIs](#rapid-api-marketplace-free-public--open-rest-apis)
	- [Apis.guru Large Archive of Sample OpenAPI Descriptions](#apisguru-large-archive-of-sample-openapi-descriptions)
- [API Managers with API Gateways & Developer Portals](#api-managers-with-api-gateways--developer-portals)
	- [API Management vs API Gateway vs Developer Portals](#api-management-vs-api-gateway-vs-developer-portals)
	- [3scale API Manager](#3scale-api-manager)
	- [Google Apigee API Manager](#google-apigee-api-manager)
	- [IBM API Connect](#ibm-api-connect)
	- [WSO2 API Manager](#wso2-api-manager)
	- [Kong API Manager](#kong-api-manager)
	- [Tyk API Manager](#tyk-api-manager)
	- [Axway API Manager](#axway-api-manager)
	- [MuleSoft API Manager](#mulesoft-api-manager)
	- [Gloo Federation API Gateway Management](#gloo-federation-api-gateway-management)
	- [Backstage Developer Portal](#backstage-developer-portal)
	- [APISIX](#apisix)
	- [NGINX as an API Gateway](#nginx-as-an-api-gateway)
	- [Lura API Gateway (based on KrakenD)](#lura-api-gateway-based-on-krakend)
	- [Spring Cloud Gateway](#spring-cloud-gateway)
- [Mobile Developer Portals](#mobile-developer-portals)
- [Automotive](#automotive)
	- [Auto API](#auto-api)
	- [Smartcar](#smartcar)
	- [Others](#others)
- [Banking](#banking)
- [Insurance](#insurance)
- [Telecom](#telecom)

## Introduction
- [Layering domains and microservices using API Gateways](https://kislayverma.com/software-architecture/layering-domains-and-microservices-using-api-gateways/)
- [ajay-yadav109458.medium.com: Concepts of API Gateway](https://ajay-yadav109458.medium.com/concepts-of-api-gateway-ac4993a0af44)
- [blog.oliverjumpertz.dev: The 10 Most Valuable Lessons I Learned As A Developer](https://blog.oliverjumpertz.dev/the-10-most-valuable-lessons-i-learned-as-a-developer)
- [genbeta.com: 32.000 desarrolladores responden sobre plataformas y lenguajes de programación: JavaScript, AWS, GitHub y Windows, los más usados](https://www.genbeta.com/desarrollo/32-000-desarrolladores-responden-plataformas-lenguajes-programacion-javascript-aws-github-windows-usados)

## API Landscape and API Marketplaces
- [API Landscape](https://www.apidays.co/api-landscape)

### API Marketplaces
- [chakray.com: API Strategy. How to create an API Marketplace](https://www.chakray.com/api-strategy-how-to-create-an-api-marketplace/)
- [rapidapi.com: What is an API Marketplace?](https://rapidapi.com/blog/api-glossary/api-marketplace/)
- [API Marketplace vs API Gateway (What’s the Difference?)](https://rapidapi.com/blog/api-marketplace-vs-api-gateway-whats-the-difference/)

### Rapid API Marketplace. Free Public & Open REST APIs
- [Rapid API:](https://rapidapi.com/) Find and Connect to Thousands of APIs. RapidAPI is the world's largest API Marketplace, is used by over one million developers to find, test, and connect to thousands of APIs — all with a single account, API Key, and SDK.
- [dzone: RapidAPI Provides API Marketplace and Insight](https://dzone.com/articles/rapidapi-provides-api-marketplace-and-insight) APIs are driving businesses and innovation.

### Apis.guru Large Archive of Sample OpenAPI Descriptions
- [apis.guru/openapi-directory: large archive of sample OpenAPI descriptions](https://apis.guru/openapi-directory/)

## API Managers with API Gateways & Developer Portals 
- [moesif.com: How to choose the right API Gateway for your platform: Comparison of Kong, Tyk, Apigee, and alternatives](https://www.moesif.com/blog/technical/api-gateways/How-to-Choose-The-Right-API-Gateway-For-Your-Platform-Comparison-Of-Kong-Tyk-Apigee-And-Alternatives/)
- [towardsdatascience.com: Building Small Services, Deploying on Kubernetes, and Integrating with API Gateway](https://towardsdatascience.com/building-small-services-deploying-on-kubernetes-and-integrating-with-api-gateway-4909db4e5282) Abstracting Backend API Authentication with Python & Redis

### API Management vs API Gateway vs Developer Portals
- **An API gateway** refers to the individual proxy server.
- **API management** refers to the overall solution of managing APIs in production which includes a **set of API gateways** acting in a cluster, an **administrative UI**, and may even include additional items such as a **developer portal for customers** to sign up and generate new API keys.
- [API Management vs API Gateway: Where Does API Analytics and Monitoring Fit?](https://dzone.com/articles/api-management-vs-api-gateway-and-where-does-api-a) 
- [API Management vs API Gateway and where does API Analytics and Monitoring fit?](https://dev.to/moesif/api-management-vs-api-gateway-and-where-does-api-analytics-and-monitoring-fit-4g75)

### 3scale API Manager
- [3scale API Manager](https://www.3scale.net/)
- [Red Hat 3scale API Management](https://www.redhat.com/en/technologies/jboss-middleware/3scale)
- [Red Hat 3Scale API Management @Youtube](https://www.youtube.com/watch?v=kBBBhpKIv9I)
- [OpenShift Ecosystem: API Management on Red Hat OpenShift with 3scale](https://blog.openshift.com/openshift-ecosystem-api-management-on-red-hat-openshift-with-3scale/)
- [Adding API Gateway Policies Now Easier With Red Hat 3scale API Management](https://developers.redhat.com/blog/2018/05/30/3scale-api-gateway-policies/)
- [Install Red Hat 3scale and configure tenants with 7 simple commands](https://developers.redhat.com/blog/2019/09/09/install-3scale-multitenant-in-7-commands/)
- [dzone: 3Scale Developer Portal Docs Per Application](https://dzone.com/articles/3scale-developer-portal-docs-per-application) Using this open source platform, we to create a more effective version of your API documentation, allowing devs to only see that docs that are relevant to their work.
- [dzone: Why Red Hat and 3scale Matter: A Developer's View](https://dzone.com/articles/why-red-hat-and-3scale-matter)
- [developers.redhat.com: New custom metrics and air gapped (restricted networks) installation in Red Hat 3scale API Management 2.9](https://developers.redhat.com/blog/2020/10/29/new-custom-metrics-and-air-gapped-installation-in-red-hat-3scale-api-management-2-9/) The 3scale Operator now fully supports air gapped installation for 3scale API Management on OpenShift. Air gapped or restricted networks are isolated from the Internet and physically isolated from any other network. Secure environments such as government agencies and financial institutions typically require an air gapped installation for Red Hat Integration on OpenShift. 
- [developers.redhat.com: Enhance application security by rotating 3scale access tokens](https://developers.redhat.com/blog/2021/04/29/enhance-application-security-by-rotating-3scale-access-tokens/)
- [developers.redhat.com: How to expose a WebSocket endpoint using Red Hat 3scale API Management](https://developers.redhat.com/articles/2021/07/01/how-expose-websocket-endpoint-using-red-hat-3scale-api-management)
- [developers.redhat.com: Simplify load balancing for API gateways using Red Hat 3scale API Management](https://developers.redhat.com/articles/2021/08/11/simplify-load-balancing-api-gateways-using-red-hat-3scale-api-management)

### Google Apigee API Manager
- [Google Apigee API Manager](https://cloud.google.com/apigee/) Apigee is an API management platform for developing, analyzing, securing & scaling various APIs and apps. It provides API technology and services for a wide range of organizations and developers to stimulate the pace of digital business. Through API, Apigee assists businesses to securely share data and services across various channels/devices in order to enhance the customer experience. Companies can manage growth and spikes in API traffic with features like traffic isolation and independent scaling.  
- [Apigee @Youtube](https://www.youtube.com/user/apigee)

### IBM API Connect
- [IBM API Connect](https://developer.ibm.com/apiconnect/)

### WSO2 API Manager 
- [WSO2 API Manager](https://wso2.com/api-management/)
- [WSO2 @Youtube](https://www.youtube.com/user/WSO2TechFlicks)

### Kong API Manager
- [Kong API Manager](https://konghq.com/kong/)
- [Kong API Platform @Youtube](https://www.youtube.com/channel/UCJfQURxlI_pQdeJUGXtA_zw)
- [medium: Kong API Gateway - From Zero to Production](https://medium.com/swlh/kong-api-gateway-zero-to-production-5b8431495ee) Let’s start by exploring the API gateway architecture pattern and then slowly deep dive into the details of running a production-grade Kong API gateway.
- [openshift.com: Modern Application Development With Kong Konnect Enterprise and Red Hat OpenShift](https://www.openshift.com/blog/modern-application-development-with-kong-konnect-enterprise-and-red-hat-openshift)

### Tyk API Manager 
- [Tyk API Manager](https://tyk.io/)
- [Tyk @Youtube](https://www.youtube.com/channel/UCe3VG8wgz03u73xiomGeQzQ)

### Axway API Manager
- [Axway API Management](https://www.axway.com/en/products/api-management/full-lifecycle-api-management)
- [Axway API Management @Youtube](https://www.youtube.com/channel/UCsRNLDnXvgtz6qsleSlVcqQ)
- [axway.com/digitize](https://axway.com/digitize)

### MuleSoft API Manager 
- [MuleSoft API Manager](https://www.mulesoft.com/platform/api/manager)
- [MuleSoft @Youtube](https://www.youtube.com/user/mulesoftvids)

### Gloo Federation API Gateway Management
- [Introducing Gloo Federation for Multi-Cluster API Gateway Management](https://www.solo.io/blog/introducing-gloo-federation-for-multi-cluster-management/)
- [solo.io: [Tutorial] Securing APIs with OIDC Using Keycloak](https://www.solo.io/blog/tutorial-gloo-integration-with-keycloak/) In this tutorial, you will learn how to integrate the Gloo API gateway with Keycloack in Kubernetes

### Backstage Developer Portal 
- [Backstage Developer Portal:](https://backstage.io/) Spotify has now open-sourced Backstage (under Apache-2.0), the platform of platforms to create a great developer experience across hundreds of squads at Spotify
- [Backstage @Youtube](https://www.youtube.com/channel/UCHBvqSwbfAf5Vx1jrwkG43Q)

### APISIX
- [apisix](https://github.com/apache/apisix)
- [thenewstack.io - APISIX: An Open Source API Gateway for Microservices](https://thenewstack.io/apisix-an-open-source-api-gateway-for-microservices/)

### NGINX as an API Gateway
- [nginx.com: Deploying NGINX as an API Gateway, Part 1 🌟](https://www.nginx.com/blog/deploying-nginx-plus-as-an-api-gateway-part-1/)

### Lura API Gateway (based on KrakenD)
- [Lura 🌟](https://luraproject.org/) An extendable, simple and stateless high-performance API Gateway framework designed for both cloud-native and on-prem setups.
- [KrakenD: The fastest API gateway comes with true linear scalability 🌟](https://www.krakend.io/) KrakenD is a stateless, distributed, high-performance API Gateway that helps you effortlessly adopt microservices.
- [krakend.io: KrakenD framework becomes a Linux Foundation project](https://www.krakend.io/blog/krakend-framework-joins-the-linux-foundation/) KrakenD framework has been donated to the Linux Foundation and is now the “Lura Project."

### Spring Cloud Gateway
- [Spring Cloud Gateway](https://spring.io/projects/spring-cloud-gateway)
- [dzone: Custom Rate Limiting for Microservices 🌟](https://dzone.com/articles/rate-limiting-for-microservices) Enforcing rate limits on microservices is a common requirement in the API economy. In this article, we are going to build a custom rate limiting solution.

## Mobile Developer Portals
- [developer.mobileconnect.io](https://developer.mobileconnect.io/)
- [developer.android.com](https://developer.android.com/)
- [developer.apple.com](https://developer.apple.com/)

## Automotive
- [medium: I want to build a car insurance app — which APIs should I use?](https://medium.com/high-mobility/i-want-to-build-a-car-insurance-app-which-apis-should-i-use-6c0998267c33)
- [medium.com: BMW CarData now integrated with Auto API](https://medium.com/high-mobility/integrate-bmw-cardata-in-the-high-mobility-platform-now-335b7d880dd6)
- [medium.com: Field test: Using the Auto API to work with BMW CarData](https://medium.com/high-mobility/field-test-using-the-auto-api-to-work-with-bmw-cardata-480c90148569)
- [medium.com: Field Test: Accessing Mercedes-Benz Data with the Auto API](https://medium.com/high-mobility/field-test-accessing-mercedes-benz-data-with-the-auto-api-a43d88363dfd)

### Auto API
- [auto-api.dev](https://auto-api.dev/)
    - [github.com/highmobility](https://github.com/highmobility)
- [high-mobility.com](https://high-mobility.com/)
    - [REST Auto API Tutorial](https://high-mobility.com/learn/tutorials/rest/)
- [High Mobility @Youtube](https://www.youtube.com/channel/UCZNjYn1NXEgPa_ENPna9Atw)

### Smartcar
- [smartcar.com](https://smartcar.com/)
- [Smartcar API for BMW](https://smartcar.com/bmw/)

### Others
- [rapidapi.com/collection/car-api](https://rapidapi.com/collection/car-api)
- [BMW InnovationLab](https://github.com/BMW-InnovationLab)

## Banking
- [Wikipedia: Open Banking](https://en.wikipedia.org/wiki/Open_banking)
- [Wikipedia: PSD2 - the Revised Payment Services Directive](https://en.wikipedia.org/wiki/Payment_Services_Directive)
    - [berlin-group.org: PSD2 Access to Bank Accounts](https://www.berlin-group.org/psd2-access-to-bank-accounts)
- [openbankingtracker.com](https://www.openbankingtracker.com/)
- [Santander APIs](https://developerhub.santander.com/)
- [BBVA API Market](https://www.bbvaapimarket.com/)
- [CaixaBank API Store](https://apistore.caixabank.com/)
- [Banco Sabadell Open API](http://docsbancosabadell.github.io/api/)
- [Deutsche Bank API Program](https://developer.db.com/)
- [TSB API Developer Portal](https://apis.developer.tsb.co.uk/)
- [ING Developer Portal](https://developer.ing.com/)
    - [ING API Marketplace](https://developer.ing.com/api-marketplace/marketplace)
- [OrangeBank API PSD2](https://orangebank.es/para-desarrolladores/)
- [Rabobank Developer Portal](https://developer.rabobank.nl/)
    - [Rabobank API Marketplace](https://developer.rabobank.nl/api-marketplace)
- [Cecabank API Market](https://apimarket.cecabank.es/)

## Insurance
- [Open Insurance](https://openinsurance.io/)
- [santalucia.es](https://api-market.santalucia.es/)

## Telecom
- [Ericsson](https://ericssondeveloperapi.portal.azure-api.net/)
- [Telefonica Thinking Cities](https://thinking-cities.readthedocs.io/)

<center>
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">What is clean code?<br><br>Clean code is the code if:<br>- it is easily readable<br>- it is easily extendable and maintainable<br>- it is as simple as possible<br>- it is cheap and risk-free to change<br>- it reveals our intent<br>- it has corresponding clean tests <br><br>What else would you add?</p>&mdash; Daniel Moka⚡ (@dmokafa) <a href="https://twitter.com/dmokafa/status/1353311679845703685?ref_src=twsrc%5Etfw">January 24, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">5 things I&#39;ve learned in 10 years as a developer:<br><br>1. No one knows exactly what they are doing<br>2. Anything can be learned with enough dedication<br>3. Perception &gt; reality<br>4. Taking on the toughest problems pays dividends<br>5. People like to make things sound complicated for their ego</p>&mdash; Nader Dabit (@dabit3) <a href="https://twitter.com/dabit3/status/1385379589615198209?ref_src=twsrc%5Etfw">April 22, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Deleting code matters! You can provide tons of value by deleting code!<br><br>Deleting code such as:<br>- removing duplication<br>- removing redundant comments<br>- removing unnecessary complexity<br>- removing unused code<br><br>Always keep in mind: The less the code, the less to maintain.</p>&mdash; Daniel Moka⚡ (@dmokafa) <a href="https://twitter.com/dmokafa/status/1389942964030480385?ref_src=twsrc%5Etfw">May 5, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Top 8 Things I Learned as a Software Engineer (Developer)...<br><br>A Thread... <a href="https://t.co/P4AMGlzYA9">pic.twitter.com/P4AMGlzYA9</a></p>&mdash; Ankur💻🎧💪 (@TheAnkurTyagi) <a href="https://twitter.com/TheAnkurTyagi/status/1396444989085782016?ref_src=twsrc%5Etfw">May 23, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">To be fullstack doesn&#39;t mean you know every part of the modern technology landscape. It means that you&#39;ve made a decision to be open to picking up the parts you need as you need them.</p>&mdash; Chris Ford (@ctford) <a href="https://twitter.com/ctford/status/1406559406804852740?ref_src=twsrc%5Etfw">June 20, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</center>