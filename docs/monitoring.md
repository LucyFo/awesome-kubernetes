# Monitoring and Performance. Prometheus, Grafana, APMs and more
- [Monitoring and Observability](#monitoring-and-observability)
    - [Key Performance Indicator (KPI)](#key-performance-indicator-kpi)
- [OpenShift Cluster Monitoring Built-in solutions](#openshift-cluster-monitoring-built-in-solutions)
    - [OpenShift 3.11 Metrics and Logging](#openshift-311-metrics-and-logging)
        - [Prometheus and Grafana](#prometheus-and-grafana)
        - [Custom Grafana Dashboard for OpenShift 3.11](#custom-grafana-dashboard-for-openshift-311)
        - [Capacity Management Grafana Dashboard](#capacity-management-grafana-dashboard)
        - [Software Delivery Metrics Grafana Dashboard](#software-delivery-metrics-grafana-dashboard)
        - [Prometheus for OpenShift 3.11](#prometheus-for-openshift-311)
    - [OpenShift 4](#openshift-4)
- [Prometheus](#prometheus)
    - [Promgen](#promgen)
    - [Promcat Resource Catalog](#promcat-resource-catalog)
    - [Prometheus Demo](#prometheus-demo)
    - [Prometheus Storage](#prometheus-storage)
    - [Prometheus SLO Service Level Objectives](#prometheus-slo-service-level-objectives)
        - [Scalability, High Availability (HA) and Long-Term Storage](#scalability-high-availability-ha-and-long-term-storage)
        - [Storage Solutions for Prometheus](#storage-solutions-for-prometheus)
            - [InfluxDB and InfluxDB Templates](#influxdb-and-influxdb-templates)
    - [Collectors. Software exposing Prometheus metrics](#collectors-software-exposing-prometheus-metrics)
        - [Prometheus Exporters. Plug-in architecture and extensibility with Prometheus Exporters (collectors)](#prometheus-exporters-plug-in-architecture-and-extensibility-with-prometheus-exporters-collectors)
        - [Prometheus Exporters Development. Node Exporter](#prometheus-exporters-development-node-exporter)
        - [Prometheus Third-party Collectors/Exporters](#prometheus-third-party-collectorsexporters)
            - [OpenTelemetry Collector](#opentelemetry-collector)
            - [Telegraf Collector](#telegraf-collector)
            - [Micrometer Collector](#micrometer-collector)
    - [Prometheus Alarms and Event Tracking](#prometheus-alarms-and-event-tracking)
    - [Prometheus and Cloud Monitoring](#prometheus-and-cloud-monitoring)
    - [Prometheus Installers](#prometheus-installers)
        - [Binaries, source code or Docker](#binaries-source-code-or-docker)
        - [Ansible Roles](#ansible-roles)
    - [Prometheus Operator](#prometheus-operator)
        - [kube Prometheus](#kube-prometheus)
        - [Prometheus Operator with Helm3](#prometheus-operator-with-helm3)
        - [Kubernetes Cluster Monitoring Stack based on Prometheus Operator](#kubernetes-cluster-monitoring-stack-based-on-prometheus-operator)
    - [Prometheus SaaS Solutions](#prometheus-saas-solutions)
- [Grafana](#grafana)
    - [Grafana Dashboards](#grafana-dashboards)
    - [Grafana Releases](#grafana-releases)
    - [Grafana Loki](#grafana-loki)
- [Proof of Concept: ActiveMQ Monitoring with Prometheus](#proof-of-concept-activemq-monitoring-with-prometheus)
    - [PoC: ActiveMQ 5.x Monitoring with Telegraf Collector, Prometheus and Grafana Dashboard 10702](#poc-activemq-5x-monitoring-with-telegraf-collector-prometheus-and-grafana-dashboard-10702)
        - [Deployment and Configuration](#deployment-and-configuration)
    - [PoC: ActiveMQ Artemis Monitoring with Prometheus Metrics Plugin (Micrometer Collector) and Prometheus. Grafana Dashboard not available](#poc-activemq-artemis-monitoring-with-prometheus-metrics-plugin-micrometer-collector-and-prometheus-grafana-dashboard-not-available)
        - [Deployment and Configuration](#deployment-and-configuration-1)
    - [Validation of Artemis Broker Monitoring with JMeter](#validation-of-artemis-broker-monitoring-with-jmeter)
        - [JMeter Example Test Plans](#jmeter-example-test-plans)
- [Kibana](#kibana)
- [Prometheus and Grafana Interactive Learning](#prometheus-and-grafana-interactive-learning)
- [Logging & Centralized Log Management](#logging--centralized-log-management)
    - [ElasticSearch](#elasticsearch)
    - [OpenSearch](#opensearch)
- [Performance](#performance)
- [List of Performance Analysis Tools](#list-of-performance-analysis-tools)
    - [Thread Dumps. Debugging Java Applications](#thread-dumps-debugging-java-applications)
- [Debugging Java Applications on OpenShift and Kubernetes](#debugging-java-applications-on-openshift-and-kubernetes)
- [Distributed Tracing. OpenTelemetry and Jaeger](#distributed-tracing-opentelemetry-and-jaeger)
    - [Microservice Observability with Distributed Tracing. OpenTelemetry.io](#microservice-observability-with-distributed-tracing-opentelemetryio)
    - [Jaeger VS OpenTelemetry. How Jaeger works with OpenTelemetry](#jaeger-vs-opentelemetry-how-jaeger-works-with-opentelemetry)
    - [Jaeger vs Zipkin](#jaeger-vs-zipkin)
    - [Grafana Tempo distributed tracing system](#grafana-tempo-distributed-tracing-system)
- [Application Performance Management (APM)](#application-performance-management-apm)
    - [Elastic APM](#elastic-apm)
    - [Dynatrace APM](#dynatrace-apm)
- [Message Queue Monitoring](#message-queue-monitoring)
    - [Red Hat AMQ 7 Broker Monitoring solutions based on Prometheus and Grafana](#red-hat-amq-7-broker-monitoring-solutions-based-on-prometheus-and-grafana)
- [Serverless Monitoring](#serverless-monitoring)
- [Distributed Tracing in Apache Beam](#distributed-tracing-in-apache-beam)
- [Krossboard Converged Kubernetes usage analytics](#krossboard-converged-kubernetes-usage-analytics)
- [Instana APM](#instana-apm)
- [Monitoring Etcd](#monitoring-etcd)
- [Zabbix](#zabbix)
- [Other Tools](#other-tools)
- [Other Awesome Lists](#other-awesome-lists)

## Monitoring and Observability
* [Wikipedia: Application Performance Index](https://en.wikipedia.org/wiki/Apdex)
* [thenewstack.io: The Challenges of Monitoring Kubernetes and OpenShift](https://thenewstack.io/the-challenges-of-monitoring-kubernetes-and-openshift/)
* [dzone.com: Kubernetes Monitoring: Best Practices, Methods, and Existing Solutions](https://dzone.com/articles/kubernetes-monitoring-best-practices-methods-and-e) Kubernetes handles containers in several computers, removing the complexity of handling distributed processing. But what's the best way to perform Kubernetes monitoring?
* [blog.cloud-mercato.com: New HTTP benchmark tool **pycurlb**](https://blog.cloud-mercato.com/new-http-benchmark-tool-pycurlb/)
* [Dzone: Comparison of Open Source API Analytics and Monitoring Tools 🌟](https://dzone.com/articles/comparison-of-open-source-api-analytics-and-monito) There are a variety of open-source projects you can leverage to build a complete API analytics platform. This articles compares them.
* [sysdig.com: Seven Kubernetes monitoring best practices every monitoring solution should enable](https://sysdig.com/blog/kubernetes-monitoring-best-practices/)
* [CNCF End User Technology Radar: Observability, September 2020 🌟](https://www.cncf.io/blog/2020/09/11/cncf-end-user-technology-radar-observability-september-2020/)
* [magalix.com: Monitoring Kubernetes Clusters Through Prometheus & Grafana 🌟](https://www.magalix.com/blog/monitoring-of-kubernetes-cluster-through-prometheus-and-grafana)
* [instana.com: The Hidden Cost of Observability: Data Volume](https://www.instana.com/blog/cf-the-hidden-cost-of-observability-data-volume/)
* [learnsteps.com: Monitoring Infrastructure System Design](https://www.learnsteps.com/monitoring-infrastructure-system-design/)
* [bravenewgeek.com: The Observability Pipeline](https://bravenewgeek.com/the-observability-pipeline/)
* [thenewstack.io: 3 Key Configuration Challenges for Kubernetes Monitoring with Prometheus](https://thenewstack.io/3-key-configuration-challenges-for-kubernetes-monitoring-with-prometheus/)
* [sysdig.com: Kubernetes Monitoring with Prometheus 🌟](https://sysdig.com/blog/kubernetes-monitoring-prometheus/)
* [sysdig.com: How to monitor kube-proxy 🌟](https://sysdig.com/blog/monitor-kube-proxy/) In this article, you will learn how to monitor kube-proxy to ensure the correct health of your cluster network.
* [thenewstack.io: Monitoring vs. Observability: What’s the Difference?](https://thenewstack.io/monitoring-vs-observability-whats-the-difference/)
* [getenroute.io: TSDB, Prometheus, Grafana In Kubernetes: Tracing A Variable Across The OSS Monitoring Stack](https://getenroute.io/blog/leverage-open-source-oss-derive-insights-grafana-prometheus-tsdb-kubernetes-standalone-api-gateway/)
* [dashbird.io: Monitoring vs Observability: Can you tell the difference? 🌟](https://dashbird.io/blog/monitoring-vs-observability/)
* [thenewstack.io: Monitoring as Code: What It Is and Why You Need It 🌟](https://thenewstack.io/monitoring-as-code-what-it-is-and-why-you-need-it/)
* [thenewstack.io: Observability Won’t Replace Monitoring (Because It Shouldn’t) 🌟](https://thenewstack.io/observability-wont-replace-monitoring-because-it-shouldnt/)
* [devopscurry.com: Understanding Container Monitoring and popular Container Monitoring Tools in 2021](https://devopscurry.com/understaning-container-monitoring-and-popular-container-monitoring-tools-in-2021/)
* [matiasmct.medium.com: Observability at Scale](https://matiasmct.medium.com/observability-at-scale-52d0d9a5fb9b)
* [dynatrace.com: How to solve the challenges of multicloud AWS, Azure and GCP observability](https://www.dynatrace.com/news/blog/how-to-solve-the-challenges-of-multicloud-aws-azure-and-gcp-observability/)
* [logz.io: Top 11 Open Source Monitoring Tools for Kubernetes 🌟](https://logz.io/blog/open-source-monitoring-tools-for-kubernetes/)
* [thenewstack.io: Kubernetes Observability Challenges in Cloud Native Architecture 🌟](https://thenewstack.io/kubernetes-observability-challenges-in-cloud-native-architecture/)
* [opsdis.com: Building a custom monitoring solution with Grafana, Prometheus and Loki](https://opsdis.com/custom-monitoring-solution-with-grafana-prometheus-and-loki/)
* [harness.io: Metrics to Improve Continuous Integration Performance](https://harness.io/blog/continuous-integration/continuous-integration-performance-metrics/)
* [thenewstack.io: Best Practices to Optimize Infrastructure Monitoring within DevOps Teams](https://thenewstack.io/best-practices-to-optimize-infrastructure-monitoring-within-devops-teams/)
* [faun.pub: DevOps Meets Observability 🌟](https://faun.pub/devops-meets-observability-78775c021b0e)
* [skilledfield.com.au: Monitoring Kubernetes and Docker Container Logs](https://skilledfield.com.au/monitoring-kubernetes-and-docker-container-logs/)
* [thenewstack.io: Growing Adoption of Observability Powers Business Transformation](https://thenewstack.io/growing-adoption-of-observability-powers-business-transformation/)
* [blog.thundra.io: What CI Observability Means for DevOps 🌟](https://blog.thundra.io/what-ci-observability-means-for-devops)
* [thenewstack.io: Monitoring API Latencies After Releases: 4 Mistakes to Avoid](https://thenewstack.io/monitoring-api-latencies-after-releases-4-mistakes-to-avoid) Find 4 common mistakes engineers make when using histograms to monitor API latencies from release to release.
* [thenewstack.io: Monitoring API Latencies After Releases: 4 Mistakes to Avoid](https://thenewstack.io/monitoring-api-latencies-after-releases-4-mistakes-to-avoid/)
* [thenewstack.io: DevOps Observability from Code to Cloud](https://thenewstack.io/devops-observability-from-code-to-cloud/)
* [ortelius.io: Microservice Monitoring and Visualization with Ortelius open source project](https://ortelius.io/blog/2021/03/26/microservice-monitoring-and-visualization/)
* [thenewstack.io: CI Observability for Effective Change Management 🌟](https://thenewstack.io/ci-observability-for-effective-change-management/)
* [thenewstack.io: Monitor Your Containers with Sysdig](https://thenewstack.io/monitor-your-containers-with-sysdig/)
* [medium: Monitoring Microservices - Part 1: Observability 🌟](https://medium.com/geekculture/monitoring-microservices-part-1-observability-b2b44fa3e67e) Achieving observability with probes, logs, metrics, and traces

### Key Performance Indicator (KPI)
* [KPIs](https://kpi.org/KPI-Basics)

## OpenShift Cluster Monitoring Built-in solutions

### OpenShift 3.11 Metrics and Logging
OpenShift Container Platform Monitoring ships with a Prometheus instance for cluster monitoring and a central Alertmanager cluster. In addition to Prometheus and Alertmanager, OpenShift Container Platform Monitoring also includes a [Grafana](https://grafana.com/) instance as well as pre-built dashboards for cluster monitoring troubleshooting. **The Grafana instance that is provided with the monitoring stack, along with its dashboards, is read-only.**

| Monitoring Component     |       Release       |                                                                                                                                                                                                                URL |
| :----------------------- | :----------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ElasticSearch            |          5          |                                                       [OpenShift 3.11 Metrics & Logging](https://docs.openshift.com/container-platform/3.11/release_notes/ocp_3_11_release_notes.html#ocp-311-metrics-and-logging) |
| Fluentd                  |        0.12         |                                                       [OpenShift 3.11 Metrics & Logging](https://docs.openshift.com/container-platform/3.11/release_notes/ocp_3_11_release_notes.html#ocp-311-metrics-and-logging) |
| Kibana                   |       5.6.13        |                                                                                                                                      [kibana 5.6.13](https://www.elastic.co/guide/en/kibana/5.6/introduction.html) |
| Prometheus               |        2.3.2        |                                 [OpenShift 3.11 Prometheus Cluster Monitoring](https://docs.openshift.com/container-platform/3.11/install_config/prometheus_cluster_monitoring.html#prometheus-cluster-monitoring) |
| Prometheus Operator      |                     |                           [Prometheus Operator technical preview](https://www.redhat.com/en/blog/generally-available-today-red-hat-openshift-container-platform-311-ready-power-enterprise-kubernetes-deployments) |
| Prometheus Alert Manager |      0.15.1         | [OpenShift 3.11 Configuring Prometheus Alert Manager](https://docs.openshift.com/container-platform/3.11/install_config/prometheus_cluster_monitoring.html#configuring-alertmanager_prometheus-cluster-monitoring) |
| Grafana                  |        5.2.3        |                                 [OpenShift 3.11 Prometheus Cluster Monitoring](https://docs.openshift.com/container-platform/3.11/install_config/prometheus_cluster_monitoring.html#prometheus-cluster-monitoring) |

#### Prometheus and Grafana
* [github.com/prometheus-operator](https://github.com/prometheus-operator)
* [redhat.com: **How to gather and display metrics in Red Hat OpenShift** (Prometheus + Grafana)](https://www.redhat.com/en/blog/how-gather-and-display-metrics-red-hat-openshift)
* [Generally Available today: Red Hat OpenShift Container Platform 3.11 is ready to power enterprise Kubernetes deployments 🌟](https://www.redhat.com/en/blog/generally-available-today-red-hat-openshift-container-platform-311-ready-power-enterprise-kubernetes-deployments)
* [The Challenges of Monitoring Kubernetes and OpenShift 3.11 🌟](https://thenewstack.io/the-challenges-of-monitoring-kubernetes-and-openshift/)
* [OCP 3.11 Metrics and Logging](https://docs.openshift.com/container-platform/3.11/release_notes/ocp_3_11_release_notes.html#ocp-311-metrics-and-logging)
* [Prometheus Cluster Monitoring 🌟](https://docs.openshift.com/container-platform/3.11/install_config/prometheus_cluster_monitoring.html)
* [Prometheus Alert Manager](https://docs.openshift.com/container-platform/3.11/install_config/prometheus_cluster_monitoring.html#configuring-alertmanager_prometheus-cluster-monitoring)
* [Leveraging Kubernetes and OpenShift for automated performance tests (part 1)](https://developers.redhat.com/blog/2018/11/22/automated-performance-testing-kubernetes-openshift/)
* [Building an observability stack for automated performance tests on Kubernetes and OpenShift (part 2) 🌟](https://developers.redhat.com/blog/2019/01/03/leveraging-openshift-or-kubernetes-for-automated-performance-tests-part-2/)
* [Promster: Use Prometheus in huge deployments with dynamic clustering and scrape sharding capabilities based on ETCD service registration](http://github.com/flaviostutz/promster)
* [developers.redhat.com: Monitoring .NET Core applications on Kubernetes](https://developers.redhat.com/blog/2020/08/05/monitoring-net-core-applications-on-kubernetes/)
* [Systems Monitoring with Prometheus and Grafana](https://flightaware.engineering/systems-monitoring-with-prometheus-grafana/)

[![openshift3 Monitoring](images/ocp_monitoring.png)](https://docs.openshift.com/container-platform/3.11/install_config/prometheus_cluster_monitoring.html)

#### Custom Grafana Dashboard for OpenShift 3.11 
By default OpenShift 3.11 Grafana is a read-only instance. Many organizations may want to add new custom dashboards. This custom grafana will interact with existing Prometheus and will also add all out-of-the-box dashboards plus few more interesting dashboards which may require from day to day operation. Custom Grafana pod uses OpenShift oAuth to authenticate users and assigns "Admin" role to all users so that users can create their own dashboards for additional monitoring.

[Getting Started with Custom Dashboarding on OpenShift using Grafana](https://github.com/redhat-cop/openshift-toolkit/tree/master/custom-dashboards). This repository contains scaffolding and automation for developing a custom dashboarding strategy on OpenShift using the OpenShift Monitoring stac

#### Capacity Management Grafana Dashboard 
[This repo](https://github.com/redhat-cop/openshift-toolkit/tree/master/capacity-dashboard) adds a capacity management Grafana dashboard. The intent of this dashboard is to answer a single question: Do I need a new node? . We believe this is the most important question when setting up a capacity management process. We are aware that this is not the only question a capacity management process may need to be able to answer. Thus, this should be considered as the starting point for organizations to build their capacity management process.

#### Software Delivery Metrics Grafana Dashboard
[This repo](https://github.com/redhat-cop/pelorus) contains tooling to help organizations measure Software Delivery and Value Stream metrics. 

#### Prometheus for OpenShift 3.11
[This repo](https://github.com/openshift/origin/tree/release-3.11/examples/prometheus) contains example components for running either an operational Prometheus setup for your OpenShift cluster, or deploying a standalone secured Prometheus instance for configurating yourself.

### OpenShift 4
OpenShift Container Platform includes a pre-configured, pre-installed, and self-updating monitoring stack that is based on the Prometheus open source project and its wider eco-system. It provides monitoring of cluster components and includes a set of alerts to immediately notify the cluster administrator about any occurring problems and a set of Grafana dashboards. The cluster monitoring stack is only supported for monitoring OpenShift Container Platform clusters.

OpenShift Cluster Monitoring components cannot be extended since they are read only. 

[Monitor your own services (technology preview)](https://docs.openshift.com/container-platform/4.3/release_notes/ocp-4-3-release-notes.html): The existing monitoring stack can be extended so you can configure monitoring for your own Services.

| Monitoring Component     | Deployed By Default | OCP 4.1  | OCP 4.2 | OCP 4.3 | OCP 4.4 |
| :----------------------- | :-----------------: | :------ | :----- | :----- | :----- |
| ElasticSearch            |         No          | 5.6.13.6 |         |         |         |
| Fluentd                  |         No          | 0.12.43  |         |         |         |
| Kibana                   |         No          |  5.6.13  |         |         |         |
| Prometheus               |         Yes         |  2.7.2   |         | 2.14.0  |  2.15.2 |
| Prometheus Operator      |         Yes         |          |         | 0.34.0  |  0.35.1 |
| Prometheus Alert Manager |         Yes         |  0.16.2  |         | 0.19.0  |  0.20.0 |
| kube-state-metrics       |         Yes         |          |         |  1.8.0  |   1.9.5 |
| Grafana                  |         Yes         |  5.4.3   |  6.2.4  |  6.4.3  |   6.5.3 |

## Prometheus
* [**prometheus.io**](https://prometheus.io/)
* [dzone.com: Monitoring with **Prometheus**](https://dzone.com/articles/monitoring-with-prometheus) Learn how to set up a basic instance of Prometheus along with Grafana and the Node Exporter to monitor a simple Linux server.
* [github.com/prometheus/prometheus](https://github.com/prometheus/prometheus)
* [Monitoring With Prometheus](https://dzone.com/articles/monitoring-with-prometheus)
* [Dzone Refcard: Scaling and Augmenting Prometheus](https://dzone.com/refcardz/scaling-and-augmenting-prometheus) Prometheus is an open-source infrastructure and services monitoring system popular for Kubernetes and cloud-native services and apps. It can help make metric collection easier, correlate events and alerts, provide security, and do troubleshooting and tracing at scale. This Refcard will teach you how to pave the path for Prometheus adoption, what observability looks like beyond Prometheus, and how Prometheus helps provide scalability, high availability, and long-term storage.
* [Monitoring Self-Destructing Apps Using Prometheus](https://dzone.com/articles/prometheus-collectors) Learn how to configure Prometheus collectors and their use cases.
* [Monitoring kubernetes with Prometheus](https://opensource.com/article/19/11/introduction-monitoring-prometheus)
* [Focus on Detection: Prometheus and the Case for Time Series Analysis](https://dzone.com/articles/focus-on-detectionprometheus-and-the-case-for-time)
* [Ensure High Availability and Uptime With Kubernetes Horizontal Pod Autoscaler (HPA) and Prometheus](https://dzone.com/articles/ensure-high-availability-and-uptime-with-kubernete)
* [Prometheus 2 Times Series Storage Performance Analyses](https://dzone.com/articles/prometheus-2-times-series-storage-performance-anal)
* [Set Up and Integrate Prometheus With Grafana for Monitoring.](https://dzone.com/articles/monitoring-using-spring-boot-20-prometheus-and-gra) How to set up and configure Prometheus and Grafana to enable application performance monitoring for REST applications.
* [Discover Applications Running on Kubernetes With Prometheus](https://dzone.com/articles/discover-applications-running-on-kubernetes-with-p)
* [Prometheus vs. Graphite: Which Should You Choose for Time Series or Monitoring?](https://dzone.com/articles/prometheus-vs-graphite-which-should-you-choose-for)
* [PromQL Tutorial](https://medium.com/@valyala/promql-tutorial-for-beginners-9ab455142085)
* [How to use Ansible to set up system monitoring with Prometheus](https://opensource.com/article/18/3/how-use-ansible-set-system-monitoring-prometheus)
* [Initial experiences with the Prometheus monitoring system](https://medium.com/@griggheo/initial-experiences-with-the-prometheus-monitoring-system-167054ac439c)
* [prometheus.io/docs/instrumenting/writing_exporters/](https://prometheus.io/docs/instrumenting/writing_exporters/)
* [devconnected.com/complete-node-exporter-mastery-with-prometheus/](https://devconnected.com/complete-node-exporter-mastery-with-prometheus/)
* [www.scalyr.com/blog/prometheus-metrics-by-example/](https://www.scalyr.com/blog/prometheus-metrics-by-example/)
* Prometheus es un "time series DBMS" y sistema de monitorización completo, que incluye recogida de datos, almacenamiento, visualización y exportación. 
* La **arquitectura de Prometheus** se basa en **"pull metrics" (extracción de métricas)**. En lugar de empujar las métricas ("pushing metrics") hacia la herramienta de monitorización, **extrae ("pull") las métricas de los servicios (por defecto un "/metrics" HTTP endpoint)** en texto plano (parseable por humanos y de fácil diagnóstico). Prometheus también tiene un "push gateway", de modo que también soporta "push" para métricas específicas cuando el modelo de "pull" no funciona (si bien este método no es recomendable).
* Prometheus se puede conectar a **series de tiempo (time series)** con un nombre de métrica y pares clave-valor, simplificando la monitorización en complejos entornos cloud multi-nodo.
* La herramienta también proporciona [PromQL](https://prometheus.io/docs/prometheus/latest/querying/basics/), para el procesado de datos "time-series". Permite realizar consultas (queries) para la manipulación de datos y generar nueva información relevante. Con [PromQL](https://prometheus.io/docs/prometheus/latest/querying/basics/) se pueden generar gráficos, visualizar conjuntos de datos, crear tablas, y generar alertas basadas en parámetros específicos. 
* La consola web de Prometheus permite gestionar todas las características y herramientas disponibles en Prometheus. Se pueden utilizar expresiones regulares y consultas avanzadas de [PromQL](https://prometheus.io/docs/prometheus/latest/querying/basics/) para la creación de conjuntos de datos (datasets) y alertas.
* Prometheus activamente "scrapea" datos, los almacena, y soporta "queries", "gráficos" y "alertas", así como proporciona "endpoints" a otros consumidores API como Grafana. Todo esto lo realiza con los siguientes componentes:
    * [Librerías cliente](https://prometheus.io/docs/instrumenting/clientlibs/): instrumentación del código de aplicación (para generar eventos).
    * [Servidor Prometheus](https://github.com/prometheus/prometheus): "scrapeando" y almacenando estos eventos, cuando se generan, como "time series data". Este es el **modelo "pull"** más común para la recogida general de métricas en Prometheus.
    * [Pushgateway](https://github.com/prometheus/pushgateway): **Modelo "Push"**, soportando trabajos efímeros de importación de datos. **Sólo recomendable en aplicaciones "serverless"**, donde las aplicaciones son lanzadas y destruidas bajo demanda, así como las aplicaciones que manejan "batch jobs". 
    * [Exportadores de Datos](https://prometheus.io/docs/instrumenting/exporters/): exportando servicios como HAProxy, StatsD, Graphite, etc.
* Prometheus se diferencia de otros sistemas de monitorización con las siguientes funcionalidades:
    *	Modelo de datos multi-dimensional, donde los "time-series data" se definen por el nombre de la métrica y dimensiones clave/valor.
    *	Nodos únicos de servidor y autónomos, sin dependencia de almacenamiento distribuido.
    *	Recogida de datos via un modelo "pull" sobre HTTP.
    *	"Time Series Data" empujado ("pushed") a otros destinos de datos vía un gateway intermediario.
    *	"Targets" descubiertos via "service discovery" ó configuración estática.
    *	Soporte de federación horizontal y vertical.
* [magalix.com: Monitoring of Kubernetes Clusters To Manage Large Scale Projects](https://www.magalix.com/blog/monitor-kuberentes-cluster-to-manage-large-scale-projects)
* [Cloud Native Monitoring with Prometheus 🌟](https://samirbehara.com/2019/05/30/cloud-native-monitoring-with-prometheus/)
* [itnext.io - Prometheus: yet-another-cloudwatch-exporter — collecting AWS CloudWatch metrics](https://itnext.io/prometheus-yet-another-cloudwatch-exporter-collecting-aws-cloudwatch-metrics-806bd34818a8)
* [medium: Kubernetes Lessons in Alerting](https://medium.com/better-programming/kubernetes-lessons-in-alerting-a0b7a455e89d) Live issues are a great opportunity to learn and improve. Here’s what happened to us
* [Prometheus Monitoring Ecosystem Begins to Mature](https://containerjournal-com.cdn.ampproject.org/c/s/containerjournal.com/topics/container-ecosystems/prometheus-monitoring-ecosystem-begins-to-mature/amp/)
* [learnsteps.com: Monitoring Infrastructure System Design](https://www.learnsteps.com/monitoring-infrastructure-system-design/)
* [ganeshvernekar.com: Prometheus TSDB (Part 1): The Head Block](https://ganeshvernekar.com/blog/prometheus-tsdb-the-head-block/)
* [ganeshvernekar.com: Prometheus TSDB (Part 2): WAL and Checkpoint](https://ganeshvernekar.com/blog/prometheus-tsdb-wal-and-checkpoint/)
* [ganeshvernekar.com: Prometheus TSDB (Part 3): Memory Mapping of Head Chunks from Disk](https://ganeshvernekar.com/blog/prometheus-tsdb-mmapping-head-chunks-from-disk/)
* [ganeshvernekar.com: Prometheus TSDB (Part 4): Persistent Block and its Index](https://ganeshvernekar.com/blog/prometheus-tsdb-persistent-block-and-its-index/)
* [youtube playlist: How to setup Prometheus 🌟](https://www.youtube.com/playlist?list=PLVx1qovxj-anCTn6um3BDsoHnIr0O2tz3)
* [learndevops.substack.com: Hitting prometheus API with curl and jq 🌟](https://learndevops.substack.com/p/hitting-prometheus-api-with-curl) **Determine offending pods that use more RAM than requested, causing OOM.**
* [devclass.com: Safety…first? Prometheus 2.24 finally features TLS on HTTP serving endpoints](https://devclass.com/2021/01/07/prometheus-2_24/)
* [sysadminxpert.com: Steps to Monitor Linux Server using Prometheus](https://sysadminxpert.com/steps-to-monitor-linux-server-using-prometheus/)
* [medium.com: Prometheus-Grafana : Node Monitoring on Kubernetes](https://medium.com/@akshitverma8191/prometheus-grafana-node-monitoring-on-kubernetes-79fd8311b56d)
* [zerodha.tech: Infrastructure monitoring with Prometheus at Zerodha](https://zerodha.tech/blog/infra-monitoring-at-zerodha/)
* [devopscube.com: How to Setup Prometheus Monitoring On Kubernetes Cluster 🌟](https://devopscube.com/setup-prometheus-monitoring-on-kubernetes/)
* [prometheus-operator.dev 🌟](https://prometheus-operator.dev) 
* [gabrieltanner.org: Golang Application monitoring using Prometheus](https://gabrieltanner.org/blog/collecting-prometheus-metrics-in-golang)
* [promlens.com 🌟](https://promlens.com/) The power tool for querying Prometheus. Build, understand, and fix your queries much more effectively with the ultimate query builder for PromQL
* [timber.io: PromQL For Humans 🌟](https://timber.io/blog/promql-for-humans)
* [medium: Prometheus monitoring with Elastic Stack in Kubernetes 🌟](https://medium.com/avmconsulting-blog/prometheus-monitoring-with-elastic-stack-in-kubernetes-5cf0aaa7ce04) Monitoring is one of the key components for managing large clusters. For this, we have several tools.
* [grafana.com: How we use metamonitoring Prometheus servers to monitor all other Prometheus servers at Grafana Labs](https://grafana.com/blog/2021/04/08/how-we-use-metamonitoring-prometheus-servers-to-monitor-all-other-prometheus-servers-at-grafana-labs/) If you rely on Prometheus for your monitoring, and your monitoring fails, how will you know? Learn how to set up Prometheus servers to monitor all other Prometheus servers
* [portworx.com: Monitoring Kubernetes Backup with Prometheus and Grafana](https://portworx.com/kubernetes-backup-monitoring/)
* [sysdig.com: Top 10 metrics in PostgreSQL monitoring with Prometheus 🌟](https://sysdig.com/blog/postgresql-monitoring/)
* [itnext.io: Observability at Scale](https://itnext.io/observability-at-scale-52d0d9a5fb9b)
* [jonbc.medium.com: Hacking your way to Observability — Part 1 : Metrics](https://jonbc.medium.com/hacking-your-way-to-observability-part-1-cf4cd42fb4dc) Starting your journey in observability by gathering metrics with Prometheus
* [innoq.com: Scraping a Docker swarm service with Prometheus](https://www.innoq.com/en/blog/scraping-docker-swarm-service-instances-with-prometheus/)
* [opensource.com: Run Prometheus at home in a container](https://opensource.com/article/21/7/run-prometheus-home-container)
* [faun.pub: Production grade Kubernetes Monitoring using Prometheus 🌟](https://faun.pub/production-grade-kubernetes-monitoring-using-prometheus-78144b835b60)
* [howtoforge.com: How to Install Prometheus System Monitoring Tool on Ubuntu 20.04](https://www.howtoforge.com/how-to-install-prometheus-on-ubuntu-20-04/)
* [cribl.io: Using Prometheus for Agentless Monitoring](https://cribl.io/blog/using-prometheus-for-agentless-monitoring/)
* [logz.io:  Guide to Monitoring AWS Lambda Metrics with Prometheus & Logz.io 🌟](https://logz.io/blog/aws-lambda-metrics-monitoring-guide/)
* [aprenderbigdata.com: Prometheus: Introducción a la Monitorización de Métricas](https://aprenderbigdata.com/prometheus/)
* [tech.marksblogg.com: Monitor ClickHouse column oriented database with Prometheus & Grafana](https://tech.marksblogg.com/clickhouse-prometheus-grafana.html)
* [karma 🌟](https://github.com/prymitive/karma) Alert dashboard for Prometheus Alertmanager
* [Alertmanager 0.23.0-rc.0 with awscloud SNS support is available for testing. There are also bugfixes and features for amtool](https://github.com/prometheus/alertmanager/releases/tag/v0.23.0-rc.0)
* [youtube: Monitoring your k6 load test: how to install Grafana and Prometheus on a Kubernetes cluster](https://www.youtube.com/watch?v=GL2v81xYuAQ&ab_channel=k6)

[![prometheus architecture](images/prometheus-architecture.png)](https://github.com/prometheus/prometheus)

### Promgen
- [Promgen 🌟](https://github.com/line/promgen) Promgen is a configuration file generator for Prometheus

### Promcat Resource Catalog
- [Promcat: A resource catalog for enterprise-class Prometheus monitoring 🌟](https://promcat.io/)

### Prometheus Demo
- [Prometheus Demo: prometheus.demo.do.prometheus.io 🌟](https://prometheus.demo.do.prometheus.io)

### Prometheus Storage
* Proporciona etiquetado clave-valor y "time-series".  La propia documentación de Prometheus explica cómo se gestiona el [almacenamiento en disco](https://prometheus.io/docs/prometheus/latest/storage/) (**Prometheus Time-Series DB**). La ingestión de datos se agrupa en bloques de dos horas, donde cada bloque es un directorio conteniendo uno o más "chunk files" (los datos), además de un fichero de metadatos y un fichero index:
* Almacenamiento de datos en disco (Prometheus Time-Series DB):
```
./data/01BKGV7JBM69T2G1BGBGM6KB12
./data/01BKGV7JBM69T2G1BGBGM6KB12/meta.json
./data/01BKGV7JBM69T2G1BGBGM6KB12/wal
./data/01BKGV7JBM69T2G1BGBGM6KB12/wal/000002
./data/01BKGV7JBM69T2G1BGBGM6KB12/wal/000001
```
* Un proceso en segundo plano compacta los bloques de dos horas en otros más grandes.
* Es posible almacenar los datos en otras soluciones de "Time-Series Database" como **InfluxDB**.

### Prometheus SLO Service Level Objectives
- [Sloth 🌟](https://github.com/slok/sloth) Easy and simple Prometheus SLO (service level objectives) generator
    - [itnext.io: SLOs should be easy, say hi to Sloth 🌟](https://itnext.io/slos-should-be-easy-say-hi-to-sloth-9c8a225df0d4)
- [PromTools: SLOs with Prometheus 🌟](https://promtools.dev/) Multiple Burn Rate Alerts. This page will generate, with the data you provide in the form, the necessary Prometheus alerting and recording rules for Multiple Burn Rate which you might know from The Site Reliability Workbook. These rules will evaluate based on the available metrics in the last 30 days. 
    - [slo-libsonnet](https://github.com/metalmatze/slo-libsonnet) Generate Prometheus alerting & recording rules and Grafana dashboards for your SLOs.
- [opensource.google: Prometheus SLO example](https://opensource.google/projects/prometheus-slo-burn-example) An end to end example of implementing SLOs with Prometheus, Grafana and Go
- [SLO Generator](https://github.com/google/slo-generator) SLO Generator is a tool to compute SLIs, SLOs, Error Budgets and Burn rate and export an SLO report to supported exporters.

#### Scalability, High Availability (HA) and Long-Term Storage
* Prometheus fue diseñado para ser fácil de desplegar. Es extremadamente fácil ponerlo en marcha, recoger algunas métricas, y empezar a construir nuestra propia herramienta de monitorización. Las cosas se complican cuando se intenta operar a un nivel de escalado considerable.
* Para entender si esto va a ser un problema, conviene plantearse las siguiente preguntas:
    -	¿Cuántas métricas puede ingerir el sistema de monitorización y cuántas son necesarias?
    -	¿Cuál es la cardinalidad de las métricas? La cardinalidad es el número de etiquetas que cada métrica puede tener. Es una cuestión muy frecuente en las métricas pertenecientes a entornos dinámicos donde a los contenedores se les asignan un ID ó nombre diferente cada vez que son lanzados, reiniciados o movidos entre nodos (caso de kubernetes).
    -	¿Es necesaria la Alta Disponibilidad (HA)?
    -	¿Durante cuánto tiempo es necesario mantener las métricas y con qué resolución? 
* La implementación de HA es laboriosa porque la funcionalidad de cluster requiere añadir plugins de terceros al servidor Prometheus. Es necesario tratar con "backups" y "restores", y el almacenamiento de métricas por un periodo de tiempo extendido hará que la base de datos crezca exponencialmente. Los servidores Prometheus proporcionan almacenamiento persistente, pero Prometheus no fue creado para el almacenamiento distribuido de métricas a lo largo de múltiples nodos de un cluster con replicación y capacidad curativa (como es el caso de Kubernetes).  Esto es conocido como **"almacenamiento a largo-plazo" (Long-Term)** y actualmente es un requisito en unos pocos casos de uso, por ejemplo en la planificación de la capacidad para monitorizar cómo la infraestructura necesita evolucionar, contracargos para facturar diferentes equipos ó departamentos para un caso específico que han hecho de la infraestructura, análisis de tendencias de uso, o adherirse a regulaciones para verticales específicos como banca, seguros, etc. 

#### Storage Solutions for Prometheus
* [monitoring2.substack.com: Big Prometheus. Thanos, Cortex, M3DB and VictoriaMetrics at scale 🌟](https://monitoring2.substack.com/p/big-prometheus)
* [**Prometheus TSDB**](https://prometheus.io/docs/prometheus/latest/storage/)
* [**Cortex**:](https://cortexmetrics.io/) Provides horizontally scalable, highly available, multi-tenant, long term storage for Prometheus. Cortex allows for storing time series data in a key-value store like Cassandra, AWS DynamoDB, or Google BigTable. It offers a Prometheus compatible query API, and you can push metrics into a write endpoint. This makes it best suited for cloud environments and multi-tenant scenarios like service providers building hosted and managed platforms.
    * [github.com/cortexproject/cortex](https://github.com/cortexproject/cortex)
    * [Weave Cortex SaaS (Hosted Prometheus - Public Cloud)](https://www.weave.works/features/prometheus-monitoring/)
* [**Thanos**:](https://thanos.io/) Open source, **highly available Prometheus setup with long term storage capabilities**. 
    * Thanos stores time series data in an object store like AWS S3, Google Cloud Storage, etc. Thanos pushes metrics through a side-car container from each Prometheus server through the gRPC store API to the query service in order to provide a global query view.
    * [github.com/ruanbekker: Thanos Cluster Setup](https://github.com/ruanbekker/thanos-cluster-setup) How to deploy a HA Prometheus setup with Unlimited Data Retention Capabilities on aws cloud S3 with Thanos Metrics.
    * [Highly Available Prometheus Metrics for Distributed SQL with Thanos on GKE](https://blog.yugabyte.com/highly-available-prometheus-metrics-for-distributed-sql-with-thanos-on-gke/)
    * [infracloud.io: Achieving multi-tenancy in monitoring with Prometheus & the mighty Thanos Receiver](https://www.infracloud.io/blogs/multi-tenancy-monitoring-thanos-receiver/)
    * [particule.io: Multi-Cluster Monitoring with Thanos](https://particule.io/en/blog/thanos-monitoring)
    * [prometheus-operator.dev: Thanos and the Prometheus Operator 🌟](https://prometheus-operator.dev/docs/operator/thanos/)
    * [Thanos Architecture Overview 🌟](https://github.com/thanos-io/thanos#architecture-overview)
    * [enmilocalfunciona.io: Aprende a configurar Thanos usando docker-compose](https://enmilocalfunciona.io/aprende-a-configurar-thanos-usando-docker-compose/)
* [**M3**:](https://www.m3db.io/) An open source, large-scale metrics platform developed by Uber. It has its own time series database, M3DB. Like Thanos, M3 also uses a side-car container to push the metrics to the DB. In addition, it supports metric deduplication and merging, and provides distributed query support.
Although it's exciting to see attempts to address the challenges of running Prometheus at scale, these are very young projects that are not widely used yet.
* [VictoriaMetrics](https://victoriametrics.com/)

##### InfluxDB and InfluxDB Templates
* [**InfluxDB**:](https://www.influxdata.com/) An [open-source time series database (TSDB)](https://en.wikipedia.org/wiki/Time_series_database) developed by InfluxData. It is written in [Go](https://en.wikipedia.org/wiki/Go_(programming_language)) and optimized for fast, high-availability storage and retrieval of [time series](https://en.wikipedia.org/wiki/Time_series) data in fields such as operations monitoring, application metrics, [Internet of Things](https://en.wikipedia.org/wiki/Internet_of_Things) sensor data, and real-time analytics. It also has support for processing data from [Graphite](https://en.wikipedia.org/wiki/Graphite_(software)).
* [en.wikipedia.org/wiki/InfluxDB](https://en.wikipedia.org/wiki/MIT_License)
* [influxdata.com: Building a Metrics & Alerts as a Service (MaaS) Monitoring Solution Using the InfluxDB Stack](https://www.influxdata.com/blog/building-a-metrics-alerts-as-a-service-maas-monitoring-solution-using-the-influxdb-stack/)
* [en.wikipedia.org/wiki/MIT_License](https://en.wikipedia.org/wiki/MIT_License)
* [dzone: Flux queries](https://dzone.com/articles/flux-windowing-and-aggregation) New language being developed at InfluxData.
* [influxdb-templates](https://www.influxdata.com/products/influxdb-templates/) Build and share InfluxDB templates for monitoring solutions that deliver faster time to awesome.
    * [thenewstack.io: Make a GitOps Workflow Using InfluxDB Templates](https://thenewstack.io/make-a-gitops-workflow-using-influxdb-templates/)
* [influxdata.com: Running InfluxDB 2.0 and Telegraf Using Docker](https://www.influxdata.com/blog/running-influxdb-2-0-and-telegraf-using-docker/)

### Collectors. Software exposing Prometheus metrics
- http://localhost:9090/targets : you should see a list of targets that you Prometheus server is scraping. 

#### Prometheus Exporters. Plug-in architecture and extensibility with Prometheus Exporters (collectors)
* Prometheus proporciona un ecosistema de **"exporters"**, los cuales permiten que herramientas de terceros puedan exportar sus datos en Prometheus. Muchos componentes de software de código abierto son compatibles por defecto. 
* [exporterhub.io 🌟](https://exporterhub.io/) Exporterhub is a curated List of Prometheus Exporters
* **Un "exporter" expone las métricas de uno ó varios "collectors".**
* [Prometheus Exporters](https://prometheus.io/docs/instrumenting/exporters/) 
    * [prometheus.io/download/](https://prometheus.io/download/)
    * [github.com/prometheus](https://github.com/prometheus)
* [Prometheus JMX Exporter 🌟](https://github.com/prometheus/jmx_exporter) A process for exposing JMX Beans via HTTP for Prometheus consumption.
* [blackbox_exporter 🌟](https://github.com/prometheus/blackbox_exporter) The blackbox exporter allows blackbox probing of endpoints over HTTP, HTTPS, DNS, TCP and ICMP.
* [Example: How to Use Prometheus Monitoring With Java to Gather Data. Gathering Java Metrics with Prometheus Monitoring (ActiveMQ)](https://www.openlogic.com/blog/prometheus-java-monitoring-and-gathering-data)
* [Maven Prometheus instrumentation library for JVM applications (client library)](https://mvnrepository.com/artifact/io.prometheus)
    * [github.com/prometheus/client_java](https://github.com/prometheus/client_java)
* [Example: JMX Exporter with ActiveMQ](https://www.openlogic.com/blog/prometheus-java-monitoring-and-gathering-data)
* [k8s-image-availability-exporter](https://github.com/flant/k8s-image-availability-exporter) is a Prometheus exporter that warns you proactively about images that are defined in Kubernetes objects (e.g., an image field in the Deployment) but are not available in the container registry (such as Docker Registry, etc.).
* [engineeringblog.yelp.com: Improving the performance of the Prometheus JMX Exporter](https://engineeringblog.yelp.com/2020/10/improving-the-performance-of-the-prometheus-jmx-exporter.html)
* [sysdig.com: How to monitor an Oracle database with Prometheus. The OracleDB Prometheus exporter](https://sysdig.com/blog/monitor-oracle-database-prometheus/)
* [YACE - yet another cloudwatch exporter 🌟](https://github.com/ivx/yet-another-cloudwatch-exporter) AWS cloudwatch to prometheus exporter - Discovers services through AWS tags, gets cloudwatch data and provides them as prometheus metrics with AWS tags as labels
* [prometheus-community/elasticsearch_exporter](https://github.com/prometheus-community/elasticsearch_exporter) Prometheus exporter for various metrics about ElasticSearch, written in Go.

#### Prometheus Exporters Development. Node Exporter
* Node exporter puede ser utilizado para exportar las métricas de nuestra aplicación ya que permite exportar un "text-file". Nuestra aplicación puede escribir datos en un fichero de texto con el formato de datos de Prometheus. Este fichero de texto con datos agregados sería exportado a Prometheus con Node Exporter. 
* [dzone.com: Monitoring Self-Destructing Apps Using Prometheus](https://dzone.com/articles/prometheus-collectors) Learn how to configure Prometheus collectors and their use cases.
* [prometheus.io: Writing Exporters](https://prometheus.io/docs/instrumenting/writing_exporters/)
* [devconnected.com: Complete Node Exporter Mastery with Prometheus](https://devconnected.com/complete-node-exporter-mastery-with-prometheus)
* [scalyr.com: Prometheus metrics by example: 5 things you can learn](https://www.scalyr.com/blog/prometheus-metrics-by-example/)
* [aws.amazon.com: Building a Prometheus remote write exporter for the OpenTelemetry Go SDK](https://aws.amazon.com/blogs/opensource/building-a-prometheus-remote-write-exporter-for-the-opentelemetry-go-sdk/)

#### Prometheus Third-party Collectors/Exporters
* Some third-party software exposes metrics in the Prometheus format, so no separate exporters are needed.
* [Prometheus Third Party Exporters](https://prometheus.io/docs/instrumenting/exporters/)
  
##### OpenTelemetry Collector
* [OpenTelemetry Collector](https://github.com/open-telemetry/opentelemetry-collector)
* [thenewstack.io: Lightstep’s OpenTelemetry Launchers Simplify Integration to Line of Code](https://thenewstack.io/lightsteps-opentelemetry-launchers-simplify-integration-to-line-of-code/) 
* [OpenTelemetry Launchers 🌟](https://github.com/search?q=org%3Alightstep+launcher)
* [thenewstack.io: Demystifying Distributed Traces in OpenTelemetry](https://thenewstack.io/demystifying-distributed-traces-in-opentelemetry/)
* [medium: OpenTelemetry Specification v1.0.0, Tracing Edition](https://medium.com/opentelemetry/opentelemetry-specification-v1-0-0-tracing-edition-72dd08936978)
* [cncf.io: From distributed tracing to APM: Taking OpenTelemetry and Jaeger up a level](https://www.cncf.io/blog/2021/04/29/from-distributed-tracing-to-apm-taking-opentelemetry-and-jaeger-up-a-level/?utm_source=thenewstack&utm_medium=twitter&utm_campaign=platform)
* [medium: Tracing in eDreams ODIGEO Lodging with Open Telemetry and Grafana Tempo](https://medium.com/edreams-odigeo-tech/tracing-in-edreams-odigeo-lodging-with-open-telemetry-and-grafana-tempo-bd1f20ddf49d)
* [newrelic.com: Understand OpenTelemetry Part 4: Instrument a Java App with OpenTelemetry](https://newrelic.com/blog/best-practices/java-opentelemetry)

<center>
<iframe src="https://www.youtube.com/embed/r8UvWSX3KA8" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

##### Telegraf Collector
* [Telegraf Collector](https://www.influxdata.com/time-series-platform/telegraf/)
* [Telegraf Prometheus Output Plugin](https://github.com/influxdata/telegraf/tree/master/plugins/outputs/prometheus_client)
* [Telegraf Ansible Role](https://github.com/rossmcdonald/telegraf)
* [Grafana Dashboards with Telegraf Collectors](https://grafana.com/grafana/dashboards?collector=Telegraf)
* [dzone: Synthetic Monitoring With Telegraf (white-box monitoring)](https://dzone.com/articles/synthetic-monitoring-with-telegraf) Monitoring based on metrics exposed by the internals of the system
* [grafana.com: Using Telegraf plugins to visualize industrial IoT data with the Grafana Cloud Hosted Prometheus service](https://grafana.com/blog/2021/04/05/using-telegraf-plugins-to-visualize-industrial-iot-data-with-the-grafana-cloud-hosted-prometheus-service/)
* [sysadminxpert.com: How to Monitor Linux System with Grafana and Telegraf](https://sysadminxpert.com/monitor-linux-system-with-grafana-and-telegraf/)
* [influxdata.com: Three Ways to Keep Cardinality Under Control When Using Telegraf](https://www.influxdata.com/blog/three-ways-to-keep-cardinality-under-control-when-using-telegraf/)

##### Micrometer Collector
* [**Micrometer** Collector](http://micrometer.io/)
* [Micrometer Prometheus](https://micrometer.io/docs/registry/prometheus)

### Prometheus Alarms and Event Tracking
* Prometheus no soporta rastreo de eventos (event tracking), pero ofrece un soporte completo de alarmas y gestión de alarmas. El lenguaje de consultas (queries) de Prometheus permite en cambio implementar rastreo de eventos por cuenta propia.

### Prometheus and Cloud Monitoring
* AWS CloudWatch is supported by Prometheus.

### Prometheus Installers
#### Binaries, source code or Docker
* [prometheus.io: Installarion](https://prometheus.io/docs/prometheus/latest/installation/)
* [prometheus.io: Getting Started](https://prometheus.io/docs/prometheus/latest/getting_started/) 
* [github.com/prometheus/prometheus](https://github.com/prometheus/prometheus)

#### Ansible Roles
- **Cloud Alchemy**: Deploy prometheus node exporter using ansible.
    - [galaxy.ansible.com/cloudalchemy/node-exporter](https://galaxy.ansible.com/cloudalchemy/node-exporter)
    - [github.com/cloudalchemy/ansible-prometheus](https://github.com/cloudalchemy/ansible-prometheus)
- [Idealista: This ansible role installs a Prometheus Node Exporter in a debian environment](https://github.com/idealista/prometheus_jmx_exporter-role)
- **Alexdzyoba**: This ansible role installs a Prometheus JMX exporter java agent in a debian nvironment. Inspired by [Idealista prometheus_jmx_exporter-role](https://github.com/dealista/prometheus_jmx_exporter-role).
    - [galaxy.ansible.com/alexdzyoba/jmx-exporter](https://galaxy.ansible.com/alexdzyoba/jmx-exporter) 
    - [github.com/alexdzyoba/ansible-jmx-exporter](https://github.com/alexdzyoba/ansible-jmx-exporter)
- **Mesaguy**: Installs and manages Prometheus and Prometheus exporters.
    - Installs and manages Prometheus server, Alertmanager, PushGateway, and numerous Prometheus exporters
    - This role was designed to allow adding new exporters with ease. Regular releases ensure it always provides the latest Prometheus software.
    - This role can register client exporters with the Prometheus server/s automatically (see tgroup management below).
    - This Ansible role will be migrated to an Ansible Collection.
    - [galaxy.ansible.com/mesaguy/prometheus](https://galaxy.ansible.com/mesaguy/prometheus)
    - [github.com/mesaguy/ansible-prometheus](https://github.com/mesaguy/ansible-prometheus)
- **William Yeh**: Prometheus for Ansible Galaxy. This role only installs 3 components: Prometheus server, Node exporter, and Alertmanager. 
    - [galaxy.ansible.com/William-Yeh/prometheus](https://galaxy.ansible.com/William-Yeh/prometheus) 
    - [github.com/William-Yeh/ansible-prometheus](https://github.com/William-Yeh/ansible-prometheus)
    - [awesomeopensource.com/project/William-Yeh/ansible-prometheus](https://awesomeopensource.com/project/William-Yeh/ansible-prometheus)
- **Undergreen**: An Ansible role that installs Prometheus Node Exporter on Ubuntu|Debian|redhat-based machines with systemd|Upstart|sysvinit.
    - [galaxy.ansible.com/UnderGreen/prometheus-node-exporter](https://galaxy.ansible.com/UnderGreen/prometheus-node-exporter) 
    - [github.com/UnderGreen/ansible-prometheus-node-exporter](https://github.com/UnderGreen/ansible-prometheus-node-exporter)
- **Mitesh Sharma**: Prometheus With Grafana Using Ansible
    - [itnext.io/prometheus-with-grafana-using-ansible-549e575c9dfa](https://itnext.io/prometheus-with-grafana-using-ansible-549e575c9dfa)
    - [github.com/MiteshSharma/PrometheusWithGrafana](https://github.com/MiteshSharma/PrometheusWithGrafana)

### Prometheus Operator 
#### kube Prometheus
* [kube-prometheus](https://github.com/coreos/kube-prometheus) Use Prometheus to monitor Kubernetes and applications running on Kubernetes.

#### Prometheus Operator with Helm3
* [devstack.in: Deploy Prometheus Operator with Helm3 and Private Registry 🌟](https://devstack.in/2020/05/25/deploy-prometheus-operator-with-helm3-and-private-registry/)

#### Kubernetes Cluster Monitoring Stack based on Prometheus Operator
- [Cluster Monitoring stack for ARM / X86-64 platforms](https://github.com/carlosedp/cluster-monitoring) Updated the cluster-monitoring stack for kubernetes to latest versions. Fresh Grafana 7, Prometheus Operator and more. This repository collects Kubernetes manifests, Grafana dashboards, and Prometheus rules combined with documentation and scripts to provide easy to operate end-to-end Kubernetes cluster monitoring with Prometheus using the Prometheus Operator.

### Prometheus SaaS Solutions
* [Weave Cortex SaaS (Hosted Prometheus - Public Cloud)](https://www.weave.works/features/prometheus-monitoring/)
* [logz.io](https://logz.io)
    * [logz.io: Logz.io’s Prometheus-as-a-Service is Generally Available 🌟](https://logz.io/blog/prometheus-as-a-service-launch/)
* [Amazon Managed Service for Prometheus](https://aws.amazon.com/prometheus/)

## Grafana
* [Grafana](https://grafana.com/) 
* Prometheus utiliza plantillas de consola para los dashboards, si bien su curva de aprendizaje de sus múltiples funcionalidades es alta, con una interfaz de usuario insuficiente. Por este motivo es muy habitual utilizar **Grafana** como interfaz de usuario.
* [grafana.com: Provisioning Grafana 🌟](https://grafana.com/docs/grafana/latest/administration/provisioning/) Las últimas versiones de Grafana permiten la creación de "datasources" y "dashboards" con Ansible, mediante las opciones de provisión de Grafana. Funciona con cualquier "datasource" (Prometheus, InfluxDB, etc), incluyendo la configuración de Grafana correspondiente y dejando poco margen para el error humano.
    * [Grafana provisioning Ansible Role](https://github.com/cloudalchemy/ansible-grafana)
* [grafana.com: Introducing the new and improved New Relic plugin for Grafana](https://grafana.com/blog/2020/07/22/introducing-the-new-and-improved-new-relic-plugin-for-grafana/)
* [Log Monitoring and Alerting with Grafana Loki](https://www.infracloud.io/blogs/grafana-loki-log-monitoring-alerting)
* [magalix.com: Monitoring Kubernetes Clusters Through Prometheus & Grafana 🌟](https://www.magalix.com/blog/monitoring-of-kubernetes-cluster-through-prometheus-and-grafana)
* [itnext.io: Monitoring Kubernetes workloads with Prometheus and Thanos](https://itnext.io/monitoring-kubernetes-workloads-with-prometheus-and-thanos-4ddb394b32c)
* [medium: Why Grafana: Part II](https://medium.com/lightspeed-venture-partners/why-grafana-part-ii-2e7e42e0f7bb)
* [scylladb.com: Building a Grafana Backend Plugin](https://www.scylladb.com/2020/10/01/building-a-grafana-backend-plugin/)
* [thenewstack.io: Grafana Adds Logging to Its Enterprise Observability Stack 🌟](https://thenewstack.io/grafana-adds-logging-to-its-enterprise-observability-stack/)
* [openshift.com: Metrics-Driven Pod Constraints](https://www.openshift.com/blog/metrics-driven-pod-constraints)
* [thenewstack.io: Grafana 7.5: Controversial Pie Charts and Loki Alerts](https://thenewstack.io/grafana-7-5-controversial-pie-charts-and-loki-alerts/)
* [zdnet.com: Grafana 8.0 integrates with Prometheus alerting](https://www.zdnet.com/article/grafana-8-0-integrates-with-prometheus-alerting/) Alerting is finally unified in the latest update of the Grafana open source stack.
* [thenewstack.io: Grafana 8.0 Rethinks Alerts and Visualizations](https://thenewstack.io/grafana-8-0-rethinks-alerts-and-visualizations/)
* [youtube.com: Grafana Loki Promtail | Grafana Loki Setup And Configuration On CentOs](https://www.youtube.com/watch?v=iqpLXUdJ0Ro&ab_channel=Thetips4you)
* [grafana.com: What's new in Grafana Cloud for July 2021: Traces, live streaming, Kubernetes and Docker integrations, and more](https://grafana.com/blog/2021/07/06/whats-new-in-grafana-cloud-for-july-2021-traces-live-streaming-kubernetes-and-docker-integrations-and-more/)

### Grafana Dashboards
* [Grafana Dashboards](https://grafana.com/grafana/dashboards)
* [github.com/mlabouardy: Grafana Dashboards](https://github.com/mlabouardy/grafana-dashboards)
* [openlogic.com: How to develop Grafana Dashboards 🌟](https://www.openlogic.com/blog/how-visualize-prometheus-data-grafana)
* [Percona Grafana dashboards for MySQL and MongoDB monitoring using Prometheus 🌟](https://github.com/percona/grafana-dashboards)
* [Prometheus Monitoring With Grafana. Prometheus Stats Dashboard and Prometheus Benchmark Dashboard](https://dzone.com/articles/prometheus-monitoring-with-grafana). How you construct your Prometheus monitoring dashboard involves trial and error. Grafana makes this exploration very easy and Prometheus has good built-in functionality.
* [Popular community plugins that can improve your Grafana dashboards 🌟](https://grafana.com/blog/2020/08/26/popular-community-plugins-that-can-improve-your-grafana-dashboards/)
* [CISCO DNA Center with Grafana Dashboard](https://hawar.no/2020/09/cisco-dna-center-with-grafana-dashboard/)
* [prskavec.net: Grafana dashboards and Jsonnet](https://www.prskavec.net/post/grafana-jsonnet/) Simple way how to make your dashboard easy to maintain.
* [percona.com: Tips for Designing Grafana Dashboards](https://www.percona.com/blog/2019/11/22/designing-grafana-dashboards/)
* [devblogs.microsoft.com:Monitoring Azure by using Grafana dashboards 🌟](https://devblogs.microsoft.com/devops/monitoring-azure-by-using-grafana-dashboards/)

Monitored Component|Collector|Dashboard Number|URL
:------------------|:-------|:---------------|------------
ActiveMQ 5.x "classic"|[Telegraf](https://www.influxdata.com/time-series-platform/telegraf/)|[10702](https://grafana.com/grafana/dashboards/10702)|[Ref1](https://docs.wavefront.com/activemq.html), [Ref2](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/activemq), [Ref3](https://github.com/prometheus/jmx_exporter/blob/master/example_configs/activemq.yml), [Ref4](https://stackoverflow.com/questions/57107282/prometheus-and-activemq-integration)
ActiveMQ Artemis/Red Hat AMQ Broker|[JMX Exporter](https://github.com/prometheus/jmx_exporter)|[9087](https://grafana.com/grafana/dashboards/9087)|[Ref1](https://github.com/prometheus/jmx_exporter/blob/master/example_configs/artemis-2.yml), [Ref2](http://techiekhannotes.blogspot.com/2018/12/artemis-monitoring-with-grafana.html), [Ref3](https://github.com/rh-messaging/artemis-prometheus-metrics-plugin)
Message Streams like Kafka/Red Hat AMQ Streams|Other|[9777](https://grafana.com/grafana/dashboards/9777)|  

### Grafana Releases
- [Open source observability, meet data transformation: Grafana 7.0 promises to connect, unify, and visualize all your data](https://www.zdnet.com/article/open-source-observability-meet-data-transformation-grafana-7-0-promises-to-connect-unify-and-visualize-all-your-data/) Grafana Labs sets the bar for open source observability with Grafana 7.0: more developer friendly, more data sources, data transformation, and growth in the cloud and on premise
- [Grafana 7.0: “We’ve built one of the best visualisation tools and it’s not tied to any one database”](https://jaxenter.com/grafana-7-0-interview-tom-wilkie-172261.html)
- [grafana.com: Grafana 8.1 released: New Geomap and Annotations panels, updated plugin management, and more](https://grafana.com/blog/2021/08/05/grafana-8.1-released-new-geomap-and-annotations-panels-updated-plugin-management-and-more/)

### Grafana Loki
- [Grafana Loki](https://grafana.com/oss/loki/)
- [itnext.io: Logging in Kubernetes with Loki and the PLG Stack](https://itnext.io/logging-in-kubernetes-with-loki-and-the-plg-stack-93b27c90ec34) Loki is a new log aggregation system from Grafana Labs. It is designed to be cost-effective and easy to operate. In this article, you learn more about Loki and how to use the PLG Stack (Promtail, Loki, Grafana) for logging in Kubernetes.

## Proof of Concept: ActiveMQ Monitoring with Prometheus 
The aim of this Proof of Concept is to learn Prometheus by example being [Red Hat AMQ 7 (broker)](https://developers.redhat.com/products/amq/overview) on RHEL the application to be monitored. Red Hat AMQ Broker is based on ActiveMQ Artemis, being this the reason why one of the following proof of concepts is done with Artemis (the other one was run in order to learn telegraf, prometheus and grafana). The same solution tested with Artemis on RHEL is valid for Red Hat AMQ 7 Broker on RHEL. 

Red Hat AMQ 7 Broker is OpenShift 3.11 compliant as Technical Preview and deployed as Operator.

Red Hat AMQ 7 Operator is fully supported in OpenShift 4.x, initially with Prometheus and Grafana monitoring already setup and maintained by AMQ Operator. It is recommended to check the metrics collected and displayed by AMQ Operator with another Proof of Concept in OpenShift 4.x. 

### PoC: ActiveMQ 5.x Monitoring with Telegraf Collector, Prometheus and Grafana Dashboard 10702
* Latest releases of Telegraf and Prometheus have been used in this Proof of Concept:
    * [telegraf-1.14.0-1 (rpm)](https://www.influxdata.com/time-series-platform/telegraf/)
    * [grafana-6.3.2-1.x86_64 (rpm)](https://grafana.com/) This is the release specified as requirement for this grafana dashboard. Newer releases of grafana are probably compliant.
    * [prometheus-2.17.1.linux-amd64 (.tar.gz)](https://prometheus.io/)
    * [apache-activemq-5.15.12 (.tar.g)](https://activemq.apache.org/components/classic/)
* References:
    * [activemq.apache.org/components/classic/documentation](https://activemq.apache.org/components/classic/documentation)
    * [grafana.com/grafana/dashboards/10702](https://grafana.com/grafana/dashboards/10702) 
    * [github.com/influxdata/telegraf/tree/master/plugins/inputs/activemq](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/activemq) 
    * [docs.wavefront.com/activemq.html](https://docs.wavefront.com/activemq.html)

#### Deployment and Configuration
* Systemd 

```
/etc/systemd/system/prometheus.service
/etc/systemd/system/activemq.service
/usr/lib/systemd/system/telegraf.service
/usr/lib/systemd/system/grafana-server.service
```

* Systemctl

```bash
systemctl daemon-reload
for service in activemq telegraf prometheus grafana-server; do systemctl status $service; done
for service in activemq telegraf prometheus grafana-server; do systemctl restart $service; done
for service in activemq telegraf prometheus grafana-server; do systemctl stop $service; done
for service in activemq telegraf prometheus grafana-server; do systemctl start $service; done
```

*  Jolokia Permissions already integrated in ActiveMQ by default. Jolokia permissions have been disabled by renaming "jolokia-access.xml" to "jolokia-access.xmlORIG" (this is a Proof of Concept):

```bash
mv /opt/activemq/webapps/api/WEB-INF/classes/jolokia-access.xml /opt/activemq/webapps/api/WEB-INF/classes/jolokia-access.xmlORIG
```

* Telegraf Jolokia Input Plugin /etc/telegraf/telegraf.d/activemq.conf 

```
[[inputs.jolokia2_agent]]
urls = ["http://localhost:8161/api/jolokia"]
name_prefix = "activemq."
username = "admin"
password = "admin"
### JVM Generic
[[inputs.jolokia2_agent.metric]]
name  = "OperatingSystem"
mbean = "java.lang:type=OperatingSystem"
paths = ["ProcessCpuLoad","SystemLoadAverage","SystemCpuLoad"]
[[inputs.jolokia2_agent.metric]]
name  = "jvm_runtime"
mbean = "java.lang:type=Runtime"
paths = ["Uptime"]
[[inputs.jolokia2_agent.metric]]
name  = "jvm_memory"
mbean = "java.lang:type=Memory"
paths = ["HeapMemoryUsage", "NonHeapMemoryUsage", "ObjectPendingFinalizationCount"]
[[inputs.jolokia2_agent.metric]]
name     = "jvm_garbage_collector"
mbean    = "java.lang:name=*,type=GarbageCollector"
paths    = ["CollectionTime", "CollectionCount"]
tag_keys = ["name"]
[[inputs.jolokia2_agent.metric]]
name       = "jvm_memory_pool"
mbean      = "java.lang:name=*,type=MemoryPool"
paths      = ["Usage", "PeakUsage", "CollectionUsage"]
tag_keys   = ["name"]
tag_prefix = "pool_"
### ACTIVEMQ
[[inputs.jolokia2_agent.metric]]
name     = "queue"
mbean    = "org.apache.activemq:brokerName=*,destinationName=*,destinationType=Queue,type=Broker"
paths    = ["QueueSize","EnqueueCount","ConsumerCount","DispatchCount","DequeueCount","ProducerCount","InFlightCount"]
tag_keys = ["brokerName","destinationName"]
[[inputs.jolokia2_agent.metric]]
name     = "topic"
mbean    = "org.apache.activemq:brokerName=*,destinationName=*,destinationType=Topic,type=Broker"
paths    = ["ProducerCount","DequeueCount","ConsumerCount","QueueSize","EnqueueCount"]
tag_keys = ["brokerName","destinationName"]
[[inputs.jolokia2_agent.metric]]
name     = "broker"
mbean    = "org.apache.activemq:brokerName=*,type=Broker"
paths    = ["TotalConsumerCount","TotalMessageCount","TotalEnqueueCount","TotalDequeueCount","MemoryLimit","MemoryPercentUsage","StoreLimi
t","StorePercentUsage","TempPercentUsage","TempLimit"]
tag_keys = ["brokerName"]
```

*  InfluxDB: Not required.
* Defautl /etc/telegraf/telegraf.conf file is modified to allow Prometheus to collect ActiveMQ metrics by pulling Telegraf metrics:

```
  # # Configuration for the Prometheus client to spawn
  [[outputs.prometheus_client]]
  #   ## Address to listen on
      listen = ":9273"
      ## Path to publish the metrics on.
      path = "/metrics"
  ...
  ...
  # # Gather ActiveMQ metrics
  [[inputs.activemq]]
  #   ## ActiveMQ WebConsole URL
  url = "http://127.0.0.1:8161"
  #   ## Credentials for basic HTTP authentication
  username = "admin"
  password = "admin"
  ...
  ...
```

* scrape_configs in /opt/prometheus/prometheus.yml 

```
  scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: 'prometheus'
      # metrics_path defaults to '/metrics'
      # scheme defaults to 'http'.
      static_configs:
      - targets: ['localhost:9090']
  - job_name: 'broker'
      static_configs:
      - targets: ['localhost:9273']
```

* Grafana Dashboard [10702](https://grafana.com/grafana/dashboards/10702) is imported from Grafana UI -> "import dashboard". Prometheus data source is connected manually with Grafana via Grafana UI.

### PoC: ActiveMQ Artemis Monitoring with Prometheus Metrics Plugin (Micrometer Collector) and Prometheus. Grafana Dashboard not available
* Latest releases of ActiveMQ Artemis and Prometheus have been used in this Proof of Concept:
    * [grafana-6.7.2-1.x86_64.rpm](https://grafana.com/)
    * [prometheus-2.17.1.linux-amd64](https://prometheus.io)
    * [apache-artemis-2.11.0](https://activemq.apache.org/components/artemis/) 
    * [apache-maven-3.6.3](https://maven.apache.org/)
* ActiveMQ Artemis can export metrics to several monitoring systems via [Artemis Prometheus Metrics Plugin](https://github.com/rh-messaging/artemis-prometheus-metrics-plugin), which uses [Micrometer Collector](https://micrometer.io/). Check [this link](http://activemq.apache.org/components/artemis/documentation/latest/metrics.html).
* Unfortunately, there's no Grafana Dashboard available for this plugin. In consequence [a new Grafana Dashboard has to be developed from scratch](https://www.openlogic.com/blog/how-visualize-prometheus-data-grafana).
* [Artemis Prometheus Metrics Plugin](https://github.com/rh-messaging/artemis-prometheus-metrics-plugin) is the recommended approach. Use [JMX Exporter](https://github.com/prometheus/jmx_exporter) to export other metrics.
* References:
    * [Apache ActiveMQ Artemis Using the Server](https://activemq.apache.org/components/artemis/documentation/latest/using-server.html)
    * [Apache ActiveMQ Artemis Management Console](https://activemq.apache.org/components/artemis/documentation/latest/management-console.html)
    * [Apache ActiveMQ Artemis Metrics](http://activemq.apache.org/components/artemis/documentation/latest/metrics.html)

#### Deployment and Configuration
* systemd

```
/etc/systemd/system/prometheus.service
/etc/systemd/system/artemis.service
/usr/lib/systemd/system/grafana-server.service
```

* systemctl

```bash
# systemctl enable artemis
# systemctl daemon-reload

 for service in artemis prometheus grafana-server; do systemctl status $service; done
 for service in artemis prometheus grafana-server; do systemctl restart $service; done
 for service in artemis prometheus grafana-server; do systemctl stop $service; done
 for service in artemis prometheus grafana-server; do systemctl start $service; done
```

* Creation of Artemis Broker

```bash
cd /var/lib
/opt/artemis/bin/artemis create --addresses 192.168.1.38 --allow-anonymous --home /opt/artemis --host <my_servername.my_domain> --http-host <my_servername.my_domain> --name <my_servername.my_domain> --queues queue1,queue2 --user artemisuser --password artemispassword artemisbroker

Creating ActiveMQ Artemis instance at: /var/lib/artemisbroker

Auto tuning journal ...
done! Your system can make 13.89 writes per millisecond, your journal-buffer-timeout will be 72000

You can now start the broker by executing:

   "/var/lib/artemisbroker/bin/artemis" run

Or you can run the broker in the background using:

   "/var/lib/artemisbroker/bin/artemis-service" start
```

* Permissions change in broker directory

```bash
# chown -R activemq. /var/lib/artemisbroker/
```

* Running artemis broker

```bash
# su - activemq
$ cd /var/lib/artemisbroker/
$ /var/lib/artemisbroker/bin/artemis run
```

* Artemis Prometehus Console Access. We can now access to Artemis Console via http://my_servername.my_domain:8161/console using the credentials specified during the CLI deployment (artemisuser / artemispassword)

* [Artemis Prometheus Plugin](https://github.com/rh-messaging/artemis-prometheus-metrics-plugin)

```bash
activemq@my_servername ~]$ pwd
/home/activemq
[activemq@my_servername ~]$ cd artemis-prometheus-metrics-plugin/
[activemq@my_servername artemis-prometheus-metrics-plugin]$ mvn install
...
[INFO] Replacing /home/activemq/artemis-prometheus-metrics-plugin/artemis-prometheus-metrics-plugin/target/artemis-prometheus-metrics-plug
in-1.0.0.CR1.jar with /home/activemq/artemis-prometheus-metrics-plugin/artemis-prometheus-metrics-plugin/target/artemis-prometheus-metrics
-plugin-1.0.0.CR1-shaded.jar
[INFO] Dependency-reduced POM written at: /home/activemq/artemis-prometheus-metrics-plugin/artemis-prometheus-metrics-plugin/dependency-re
duced-pom.xml
[INFO]
[INFO] --- maven-install-plugin:2.4:install (default-install) @ artemis-prometheus-metrics-plugin ---
[INFO] Installing /home/activemq/artemis-prometheus-metrics-plugin/artemis-prometheus-metrics-plugin/target/artemis-prometheus-metrics-plu
gin-1.0.0.CR1.jar to /home/activemq/.m2/repository/org/apache/activemq/artemis-prometheus-metrics-plugin/1.0.0.CR1/artemis-prometheus-metr
ics-plugin-1.0.0.CR1.jar
[INFO] Installing /home/activemq/artemis-prometheus-metrics-plugin/artemis-prometheus-metrics-plugin/dependency-reduced-pom.xml to /home/a
ctivemq/.m2/repository/org/apache/activemq/artemis-prometheus-metrics-plugin/1.0.0.CR1/artemis-prometheus-metrics-plugin-1.0.0.CR1.pom
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for artemis-prometheus-metrics-pom 1.0.0.CR1:
[INFO]
[INFO] artemis-prometheus-metrics-pom ..................... SUCCESS [  0.328 s]
[INFO] ActiveMQ Artemis Prometheus Metrics Plugin Servlet . SUCCESS [  7.964 s]
[INFO] ActiveMQ Artemis Prometheus Metrics Plugin ......... SUCCESS [ 34.596 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  43.030 s
[INFO] Finished at: 2020-04-10T13:36:27+02:00
[INFO] ------------------------------------------------------------------------
```

* New artifact is copied to artemis broker. Artefact artemis-prometheus-metrics-plugin/target/artemis-prometheus-metrics-plugin-VERSION.jar is copied to our broker:  

```bash
[activemq@my_servername artemis-prometheus-metrics-plugin]$ cp artemis-prometheus-metrics-plugin/target/artemis-prometheus-metrics-plugin-
1.0.0.CR1.jar /var/lib/artemisbroker/lib/
```

* Edition of file /var/lib/artemisbroker/etc/broker.xml

```
<metrics-plugin class-name="org.apache.activemq.artemis.core.server.metrics.plugins.ArtemisPrometheusMetricsPlugin"/>
``` 

* Creation of <artemis_instance>/web

```
[activemq@my_servername artemisbroker]$ mkdir /var/lib/artemisbroker/web
```

* Artifact artemis-prometheus-metrics-plugin-servlet/target/metrics.war is copied to <ARTEMIS_INSTANCE>/web :

```bash
[activemq@my_servername artemis-prometheus-metrics-plugin]$ cp artemis-prometheus-metrics-plugin-servlet/target/metrics.war /var/lib/artem
isbroker/web/
```

* Below web component added to <ARTEMIS_INSTANCE>/etc/bootstrap.xml :

```
[activemq@my_servername artemis-prometheus-metrics-plugin]$ vim /var/lib/artemisbroker/etc/bootstrap.xml
...
<app url="metrics" war="metrics.war"/>
...

```

* Restart of Artemis Broker
* Prometheus configuration, scrape_configs in /opt/prometheus/prometheus.yml :

```
scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: 'prometheus'

    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.

    static_configs:
    - targets: ['localhost:9090']
  - job_name: 'broker'
    static_configs:
    - targets: ['localhost:8161']
```

* Last step: Apparently there's not Grafana Dashboard available for this use case. It is required to [develop a new Grafana Dashboard](https://www.openlogic.com/blog/how-visualize-prometheus-data-grafana).

### Validation of Artemis Broker Monitoring with JMeter
* In order to validate our Artemis Broker Monitoring solution we need to "inject traffic/data/metrics" with for example Pub/Sub messages. 
* We can achieve this with a little of java code or by sending messages via Artemis Web Console -> **"Operations"** tab. 
* Another option is running the jmeter test plans available on [Artemis' github repo](https://github.com/apache/activemq-artemis/tree/master/examples/perf/jmeter). The procedure is described below. Remember to create the queues and addresses (topics) defined in jmeter example test plans.

#### JMeter Example Test Plans 
* Latest release of [Apache JMeter](https://jmeter.apache.org/) deployed in /opt
* Library artemis-jms-client-all-2.11.0.jar is copied to $JMETER_HOME/lib :

```bash
$ cp /opt/artemis/lib/client/artemis-jms-client-all-2.11.0.jar /opt/apache-jmeter-5.2.1/lib/
```

* jndi.properties file is modified with Artemis' IP address (it is not listening on localhost):

```
$ vim /opt/artemis/examples/perf/jmeter/jndi.properties
$ cat /opt/artemis/examples/perf/jmeter/jndi.properties
connectionFactory.ConnectionFactory=tcp://192.168.1.38:61616
```

* jndi.properties is packaged in a jar file and moved to $JMETER_HOME/lib :

```
[activemq@my_servername ~]$ cd /opt/artemis/examples/perf/jmeter/
[activemq@my_servername jmeter]$ ls -l
total 28
-rw-rw-r-- 1 activemq activemq 11887 Jan 10 16:22 1.jms_p2p_test.jmx
-rw-rw-r-- 1 activemq activemq  8442 Jan 10 16:22 2.pub_sub_test.jmx
-rw-rw-r-- 1 activemq activemq   833 Jan 10 16:22 jndi.properties
[activemq@my_servername jmeter]$ jar -cf artemis-jndi.jar jndi.properties
[activemq@my_servername jmeter]$ ls -l
total 32
-rw-rw-r-- 1 activemq activemq 11887 Jan 10 16:22 1.jms_p2p_test.jmx
-rw-rw-r-- 1 activemq activemq  8442 Jan 10 16:22 2.pub_sub_test.jmx
-rw-rw-r-- 1 activemq activemq   946 May 15 08:46 artemis-jndi.jar
-rw-rw-r-- 1 activemq activemq   833 Jan 10 16:22 jndi.properties
[activemq@my_servername jmeter]$ cp artemis-jndi.jar /opt/apache-jmeter-5.2.1/lib/
```

* Example Test Plans available at Artemis GitHub Repo are run by JMeter (from within the GUI or the CLI):

```
[activemq@my_servername ~]$ cd /opt/artemis/examples/perf/jmeter/
[activemq@my_servername jmeter]$ ls -la
total 32
drwxrwxr-x 2 activemq activemq   101 May 15 08:46 .
drwxrwxr-x 3 activemq activemq    19 Jan 10 16:22 ..
-rw-rw-r-- 1 activemq activemq 11887 Jan 10 16:22 1.jms_p2p_test.jmx
-rw-rw-r-- 1 activemq activemq  8442 Jan 10 16:22 2.pub_sub_test.jmx
-rw-rw-r-- 1 activemq activemq   946 May 15 08:46 artemis-jndi.jar
-rw-rw-r-- 1 activemq activemq   833 Jan 10 16:22 jndi.properties
[activemq@my_servername jmeter]$
[activemq@my_servername bin]$ cd
[activemq@my_servername ~]$ pwd
/home/activemq
[activemq@my_servername ~]$ /opt/apache-jmeter-5.2.1/bin/jmeter.sh -n -t /opt/artemis/examples/perf/jmeter/1.jms_p2p_test.jmx -l results-file-1.txt -j 1.log
[activemq@my_servername ~]$ /opt/apache-jmeter-5.2.1/bin/jmeter.sh -n -t /opt/artemis/examples/perf/jmeter/2.pub_sub_test.jmx -l results-file-2.txt -j 2.log

```

* We can now see metrics displayed on Grafana and Artemis Dashboard:

JMeter|Artemis Grafana|Artemis Dashboard
:-------:|:---------:|:-------:
![jmeter artemis](images/jmeter_artemis.png)|![artemis grafana](images/artemis_grafana.png)|![artemis dashboard monitoring](images/artemis_dashboard_mon.png)

## Kibana
* [Kibana](https://www.elastic.co/kibana)
    * [Kibana Docs](https://www.elastic.co/guide/index.html)
* [dzone: Kibana Tutorial: Part 1 - Getting Started](https://dzone.com/articles/kibana-tutorial-getting-started-part-1)
    * [dzone: Kibana Tutorial: Part 2 - Creating Visualizations](https://logz.io/blog/kibana-tutorial-2/)
* [dzone: Getting Started With Kibana Advanced Searches](https://dzone.com/articles/getting-started-with-kibana-advanced-searches)
* [dzone: Kibana Hacks: 5 Tips and Tricks](https://dzone.com/articles/kibana-hacks-5-tips-and-tricks)
* [juanonlab.com: Dashboards de Kibana](https://www.juanonlab.com/blog/es/dashboards-de-kibana)
* [skedler.com: Kibana Customization – The brilliant beginner’s guide to simplifying Kibana for non-technical users](https://www.skedler.com/blog/kibana-customization-brilliant-beginners-guide-simplifying-kibana-non-technical-users/)
* [dev.to: Beginner's guide to understanding the relevance of your search with Elasticsearch and Kibana](https://dev.to/lisahjung/beginner-s-guide-to-understanding-the-relevance-of-your-search-with-elasticsearch-and-kibana-29n6)

## Prometheus and Grafana Interactive Learning
* [katacoda.com: Getting Started with Prometheus](https://www.katacoda.com/courses/prometheus/getting-started)
* [katacoda.com: Creating Dashboards with Grafana](https://www.katacoda.com/courses/prometheus/creating-dashboards-with-grafana)

## Logging & Centralized Log Management
- [devops.com: How Centralized Log Management Can Save Your Company](https://devops.com/how-centralized-log-management-can-save-your-company/)

### ElasticSearch
- [pythonsimplified.com: Elasticsearch Core Concepts Explained](https://pythonsimplified.com/elasticsearch-core-concepts-explained/)
- [zdnet.com: AWS, as predicted, is forking Elasticsearch](https://www.zdnet.com/article/aws-as-predicted-is-forking-elasticsearch/) Amazon Web Services, however, isn't the only one who dislikes Elastic's move to relicense Elasticsearch under the non-open-source Server Side Public License.
- [amazon.com: Stepping up for a truly open source Elasticsearch](https://aws.amazon.com/blogs/opensource/stepping-up-for-a-truly-open-source-elasticsearch/)
- [Store NGINX access logs in Elasticsearch with Logging operator 🌟](https://banzaicloud.com/docs/one-eye/logging-operator/quickstarts/es-nginx/) This guide describes how to collect application and container logs in Kubernetes using the Logging operator, and how to send them to Elasticsearch.
    - [Rancher Logging Operator 🌟](https://rancher.com/docs/rancher/v2.x/en/logging/v2.5/)
- [blog.streammonkey.com: How We Serverlessly Migrated 1.58 Billion Elasticsearch Documents](https://blog.streammonkey.com/how-we-serverlessly-migrated-1-58-billion-elasticsearch-documents-33ad3d0d7c4f)
- [youtube: ELK for beginners - by XavkiEn 🌟](https://www.youtube.com/playlist?list=PLWZKNB9waqIX00uj5q4nX_TOFiX3if1z3)
- [blog.bigdataboutique.com: Tuning Elasticsearch: The Ideal Java Heap Size](https://blog.bigdataboutique.com/2021/07/tuning-elasticsearch-the-ideal-java-heap-size-2toq2j)

### OpenSearch
- [opensearch.org 🌟](https://opensearch.org/)
- [amazon.com: Introducing OpenSearch](https://aws.amazon.com/blogs/opensource/introducing-opensearch/)
- [logz.io: Logz.io Announces Support for OpenSearch; A Community-driven Open Source Fork of Elasticsearch and Kibana](https://logz.io/news-posts/logz-io-announces-support-for-opensearch-a-community-driven-open-source-fork-of-elasticsearch-and-kibana/)
- [techrepublic.com: OpenSearch: AWS rolls out its open source Elasticsearch fork](https://www.techrepublic.com/article/opensearch-aws-rolls-out-its-open-source-elasticsearch-fork/)
- [thenewstack.io: This Week in Programming: AWS Completes Elasticsearch Fork with OpenSearch](https://thenewstack.io/this-week-in-programming-aws-completes-elasticsearch-fork-with-opensearch/)
- [logz.io: OpenSearch Is Now Generally Available!](https://logz.io/blog/opensearch-1-0-ga-generally-available-elasticsearch-kibana-fork/)
- [thenewstack.io: This Week in Programming: The ElasticSearch Saga Continues](https://thenewstack.io/this-week-in-programming-the-elasticsearch-saga-continues/)
- [aws.amazon.com: Keeping clients of OpenSearch and Elasticsearch compatible with open source](https://aws.amazon.com/blogs/opensource/keeping-clients-of-opensearch-and-elasticsearch-compatible-with-open-source/)

## Performance
* [dzone.com: The Keys to Performance Tuning and Testing](https://dzone.com/articles/the-keys-to-performance-tuning-and-testing)
* [dzone.com: How Performance Tuning and Testing are Changing](https://dzone.com/articles/how-performance-tuning-and-testing-are-changing)
* [Performance Patterns in Microservices-Based Integrations 🌟](https://dzone.com/articles/performance-patterns-in-microservices-based-integr-1) Almost all applications that perform anything useful for a given business need to be integrated with one or more applications. With microservices-based architecture, where a number of services are broken down based on the services or functionality offered, the number of integration points or touch points increases massively.

## List of Performance Analysis Tools
* Threadumps + heapdumps + GC analysis tools
* [en.wikipedia.org/wiki/List_of_performance_analysis_tools](https://en.wikipedia.org/wiki/List_of_performance_analysis_tools)
* [InspectIT](https://en.wikipedia.org/wiki/InspectIT)
* [VisualVM 🌟](https://en.wikipedia.org/wiki/VisualVM)
* [OverOps](https://en.wikipedia.org/wiki/OverOps)
* [FusionReactor](https://en.wikipedia.org/wiki/FusionReactor)
* [tier1app.com](https://tier1app.com/)
* [fastthread.io 🌟](https://fastthread.io/)
* [gceasy.io 🌟](https://gceasy.io/)
* [heaphero.io](https://heaphero.io/)

### Thread Dumps. Debugging Java Applications
- [How to read a Thread Dump](https://dzone.com/articles/how-to-read-a-thread-dump)
- [Performance Patterns in Microservices-Based Integrations 🌟](https://dzone.com/articles/performance-patterns-in-microservices-based-integr-1) **A must read!**
- [Dzone: how to take thread dumps](https://dzone.com/articles/how-to-take-thread-dumps-7-options)
- Thread Dump Analyzers: [fastThread](https://fastthread.io/), [Spotify TDA](https://spotify.github.io/threaddump-analyzer/), [IBM Thread and Monitor Dump Analyzer for Java](https://www.ibm.com/support/pages/ibm-thread-and-monitor-dump-analyzer-java-tmda), [TDA - Thread Dump Analyzer](https://github.com/irockel/tda)
- [blog.arkey.fr: Using JDK FlightRecorder and JDK Mission Control](https://blog.arkey.fr/2020/06/28/using-jdk-flight-recorder-and-jdk-mission-control/)
- [FastThread.io](https://fastthread.io/): Thread dumps can be uploaded via Web or API Call from within the POD (jstack must be available within the container):

```bash
#!/bin/sh
# Generate N thread dumps of the process PID with an INTERVAL between each dump.
if [ $# -ne 3 ]; then
   echo Generates Java thread dumps using the jstack command.
   echo
   echo usage: $0 process_id repetitions interval
   exit 1
fi 
PID=$1
N=$2
INTERVAL=$3 
for ((i=1;i<=$N;i++))
do
   d=$(date +%Y%m%d-%H%M%S)
   dump="threaddump-$PID-$d.txt"
   echo $i of $N: $dump
   jstack -l $PID > $dump
   curl -X POST --data-binary @./$dump https://fastthread.io/fastthread-api?apiKey=<APIKEY> --header "Content-Type:text"
   sleep $INTERVAL
done
```

- How to run this script from within the POD: ```./script_thread_dump.sh 1 15 3```, where:
    - “1”: PID of java process (“1” in containers running a single process, check with “ps ux” command).
    - “15”: 15 repetitions or thread dumps
    - “3”: interval of 3 seconds between each thread dump.
- According to some references only 3 thread dumps captured in a timeframe of 10 seconds is necessary (when we want to troubleshoot a Java issue during a service degradation).
- Sample thread dump analysis reports generated by fastThread: 
    - [Transitive blocks](https://fastthread.io/ft-thread-report.jsp?dumpId=1&s=t) 
    - [Unresponsive JVM](https://fastthread.io/ft-thread-report.jsp?dumpId=1&s=t) 
    - [Sudden CPU spike](https://fastthread.io/ft-thread-report.jsp?dumpId=1&s=t)
    - [Thread Leaks](https://fastthread.io/ft-thread-report.jsp?dumpId=1&s=t)

## Debugging Java Applications on OpenShift and Kubernetes
- [developers.redhat.com: Troubleshooting java applications on openshift (Jolokia)](https://developers.redhat.com/blog/2017/08/16/troubleshooting-java-applications-on-openshift/)
- [Debugging Java Applications On OpenShift and Kubernetes](https://www.openshift.com/blog/debugging-java-applications-on-openshift-kubernetes)
- [Remote Debugging of Java Applications on OpenShift](https://servicesblog.redhat.com/2019/03/06/remote-debugging-of-java-applications-on-openshift/)
    - [Dzone: Remote Debugging of Java Applications on OpenShift (JMX + VisualVM)](https://dzone.com/articles/remote-debugging-of-java-applications-on-openshift) 
- [VisualVM: JVisualVM to an Openshift pod](https://fedidat.com/250-jvisualvm-openshift-pod/)  
- [redhat.com: How do I analyze a Java heap dump?](https://access.redhat.com/solutions/18301)

## Distributed Tracing. OpenTelemetry and Jaeger
- [Microservice Observability with Distributed Tracing: **OpenTelemetry.io** 🌟](https://opentelemetry.io/) (**OpenTracing.io + OpenCensus.io = OpenTelemetry.io**)
- [**Jaeger** 🌟](https://www.jaegertracing.io/)
     - [Jaeger Demo1](https://github.com/obitech/micro-obs)
     - [Jaeger Demo 2](https://github.com/open-telemetry/opentelemetry-collector/tree/master/examples/demo)
     - [medium.com: **Jaeger embraces OpenTelemetry collector** 🌟](https://medium.com/jaegertracing/jaeger-embraces-opentelemetry-collector-90a545cbc24)
     - [Best Practices for Deploying Jaeger on Kubernetes in Production](https://thenewstack.io/best-practices-for-deploying-jaeger-on-kubernetes-in-production/)
- [**zipkin.io**](https://zipkin.io/)
- [**OpenTracing.io**](https://opentracing.io/)
     - [lightstep.com: Understand Distributed Tracing](https://docs.lightstep.com/docs/understand-distributed-tracing)
- [grafana.com: A beginner's guide to distributed tracing and how it can increase an application's performance 🌟](https://grafana.com/blog/2021/01/25/a-beginners-guide-to-distributed-tracing-and-how-it-can-increase-an-applications-performance/)
- [awkwardferny.medium.com: Setting up Distributed Tracing in Kubernetes with OpenTracing, Jaeger, and Ingress-NGINX](https://awkwardferny.medium.com/setting-up-distributed-tracing-with-opentelemetry-jaeger-in-kubernetes-ingress-nginx-cfdda7d9441d)
- [ploffay.medium.com: Five years evolution of open-source distributed tracing 🌟](https://ploffay.medium.com/five-years-evolution-of-open-source-distributed-tracing-ec1c5a5dd1ac)

### Microservice Observability with Distributed Tracing. OpenTelemetry.io
- Used for monitoring and troubleshooting microservices-based distributed systems.
- [OpenTelemetry.io](https://opentelemetry.io/): 
    - **Unified standard** (open, vendor-neutral API), **merge of [OpenCensus.io](https://opencensus.io/) and [OpenTracing.io](https://opentracing.io/)**. 
    - “A single set of system components and language-specific telemetry libraries” to standardize how the industry uses metrics, traces, and eventually logs to enable observability. 
- A major component of the [OpenTelemetry specification](https://github.com/open-telemetry/opentelemetry-specification) is **distributed tracing**. 
- **Tracing** is about analyzing, recording, and describing transactions.
- **Distributed Tracing:** Troubleshooting requests between interconnected cloud-based microservices can’t always be done with logs and metrics alone. This is where distributed tracing comes into play: It provides developers with a  detailed view of individual requests as they “hop” through a system of microservices. With **distributed tracing** you can:
    - Trace the path of a request as it travels across a complex system.
    - Discover the latency of the components along that path.
    - Know which component in the path is creating a bottleneck or failure.
- **Performance:** Latency is a very important metric in microservices. Latency problems in one service will impact the overall request latency when chaining calls to different microservices. Every call to a microservice should record a trace, which is basically a record of how much time it took to respond. It's possible to add more details to the function level, including the action, the result, and the pass to the next service. The hard part is triaging all traces in a request from a client. Usually, a trace ID header has to be sent in every request. If there isn't one, the logging library creates it and it will represent the first trace in a request. **Adding traces with [OpenCensus](https://opencensus.io/) is simply a matter of including the libraries and registering an exporter.** 
- **Monitoring in a Microservices/Kubernetes World:** In distributed system architectures like microservices, having visibility from different perspectives will be critical at troubleshooting time. Many things could happen in a request when there are many parts constantly interacting at the same time. The most common method is to write logs to the stdout and stderr streams.
    - For example, a latency problem in the system could exist because a microservice is not responding correctly. Maybe Kubernetes is restarting the pod too frequently, or perhaps the cluster is out of capacity and can't schedule any more pods. But for this reason, tools like [Istio](https://istio.io/) exist; by injecting a container in every pod, you can get a pretty good baseline of telemetry. Additionally, when you add instrumentation with libraries like [OpenCensus](https://opencensus.io/), you can deeply understand what's happening with and within each service.
    - All this information will need a storage location, and as a good practice, you might want to have it a centralized location to provide access to anyone in the team — not just for the operations team.
- **Older Distributed Tracing Solutions:** 
    - [Dapper](https://research.google/pubs/pub36356/) (Google)
    - [Zipkin](https://zipkin.io/) (A.K.A. OpenZipkin, created by Twitter, inspired by Dapper)
    - [Jaeger](https://www.jaegertracing.io/) (Uber Technologies, inspired by Dapper & Zipkin)
    - etc.
- [Medium: Distributed Tracing and Monitoring using OpenCensus](https://medium.com/@rghetia/distributed-tracing-and-monitoring-using-opencensus-fe5f6e9479fb)
- [Dzone: Zipkin vs. Jaeger: Getting Started With Tracing](https://dzone.com/articles/zipkin-vs-jaeger-getting-started-with-tracing) Learn about Zipkin and Jaeger, how they work to add request tracing to your logging routine, and how to choose which one is the right fit for you.
- [opensource.com: Distributed tracing in a microservices world](https://opensource.com/article/18/9/distributed-tracing-microservices-world) What is distributed tracing and why is it so important in a microservices environment?
- [opensource.com: 3 open source distributed tracing tools](https://opensource.com/article/18/9/distributed-tracing-tools) Find performance issues quickly with these tools, which provide a graphical view of what's happening across complex software systems.
- [newrelic.com: OpenTracing, OpenCensus, OpenTelemetry, and New Relic (Best overview of OpenTelemetry)](https://blog.newrelic.com/engineering/opentelemetry-opentracing-opencensus/)  
- There’s no OpenTelemetry UI, instead Jaeger UI (or any APM like Dynatrace or New Relic) can be used as “Tracing backend + Visualization frontend + Data mining platform” of OpenTelemetry API/SDK.
- [thenewstack.io: Tracing: Why Logs Aren’t Enough to Debug Your Microservices 🌟](https://thenewstack.io/tracing-why-logs-arent-enough-to-debug-your-microservices/)

<center>
[![Jaeger UI](images/jaeger_ui.png)](https://www.jaegertracing.io/)

[![Zipking UI](images/zipkin_ui.png)](https://zipkin.io/)
</center>
<br/>

### Jaeger VS OpenTelemetry. How Jaeger works with OpenTelemetry
- [medium: Jaeger VS OpenTracing VS OpenTelemetry](https://medium.com/jaegertracing/jaeger-and-opentelemetry-1846f701d9f2)
- [medium: Using Jaeger and OpenTelemetry SDKs in a mixed environment with W3C Trace-Context](https://medium.com/jaegertracing/jaeger-clients-and-w3c-trace-context-c2ce1b9dc390)

![Jaeger Vs OpenTelemetry](images/jaeger_vs_opentelemetry.png)

### Jaeger vs Zipkin
- [thenewstack.io: Jaeger vs. Zipkin: Battle of the Open Source Tracing Tools](https://thenewstack.io/jaeger-vs-zipkin-battle-of-the-open-source-tracing-tools/)

### Grafana Tempo distributed tracing system
- [Grafana Tempo](https://github.com/grafana/tempo) Grafana Tempo is an open source, easy-to-use and high-scale distributed tracing backend. Tempo requires only object storage to operate and is deeply integrated with Grafana, Prometheus, and Loki.
- [grafana.com: Announcing Grafana Tempo, a massively scalable distributed tracing system 🌟](https://grafana.com/blog/2020/10/27/announcing-grafana-tempo-a-massively-scalable-distributed-tracing-system/)
- [opensource.com: Get started with distributed tracing using Grafana Tempo](https://opensource.com/article/21/2/tempo-distributed-tracing) Grafana Tempo is a new open source, high-volume distributed tracing backend.

## Application Performance Management (APM)
- [APM in wikipedia](https://en.wikipedia.org/wiki/Application_performance_management): The monitoring and management of performance and availability of software applications. APM strives to detect and diagnose complex application performance problems to maintain an expected level of service. APM is "the translation of IT metrics into business meaning.” 
- Tip: [Download APM report from IT Central Station](https://www.itcentralstation.com/categories/application-performance-management-apm)
* [Awesome APM 🌟](https://github.com/antonarhipov/awesome-apm)
* [dzone.com: APM Tools Comparison](https://dzone.com/articles/apm-tools-comparison-which-one-should-you-choose)
* [dzone.com: Java Performance Monitoring: 5 Open Source Tools You Should Know](https://dzone.com/articles/java-performance-monitoring-5-open-source-tools-you-should-know)
* [dzone.com: 14 best performance testing tools and APM solutions](https://dzone.com/articles/14-best-performance-testing-tools-and-apm-solution)
* Exception Tracking:
    * [sentry.io](https://sentry.io/)
    * APMs like Dynatrace, etc.
* APM Tools:
    * [datadoghq.com](https://www.datadoghq.com/)
    * [honeycomb.io](https://www.honeycomb.io)
    * [lightstep.com](https://lightstep.com)
    * [skywalking.apache.org 🌟](https://skywalking.apache.org/)
        * [tetrate.io: SkyWalking 8.4 provides infrastucture monitoring for VMs](https://www.tetrate.io/blog/27835-revision-v1/)   
        * [thenewstack.io: End-User Tracing in a SkyWalking-Observed Browser](https://thenewstack.io/end-user-tracing-in-a-skywalking-observed-browser/)
    * [AppDynamics 🌟](https://www.appdynamics.com/)
    * [New Relic 🌟](https://newrelic.com/)
    * [Dynatrace 🌟](https://www.dynatrace.com/)
    * [SigNoz 🌟](https://github.com/SigNoz/signoz) SigNoz helps developers monitor their applications & troubleshoot problems, an open-source alternative to DataDog, NewRelic, etc. 

### Elastic APM
- [Elastic APM](https://www.elastic.co/products/apm)
- [Elastic APM Server](https://www.elastic.co/guide/en/apm/get-started/current/components.html): 
- [Mininimum elasticsearch requirement is 6.2.x or higher](https://www.elastic.co/support/matrix#matrix_compatibility)
- Built-in elasticsearch 5.6 in Openshift 3 & Openshift 4 cannot be integrated with Elastic APM Server.
- Solutions: Deploy a higher version of [Elasticsearch + Kibana](https://hub.docker.com/_/elasticsearch) on a new Project dedicated to Elastic APM; or setup an Elastic Cloud account.
- [Elastic APM Server Docker image](https://github.com/sls-dev1/openshift-elastic-apm-server) (“oss” & openshift compliant). 
- [elastic.co: Using the Elastic APM Java Agent on Kubernetes](https://www.elastic.co/blog/using-elastic-apm-java-agent-on-kubernetes-k8s)
- [Monitoring Java applications with Elastic: Getting started with the Elastic APM Java Agent](https://www.elastic.co/blog/monitoring-java-applications-and-getting-started-with-the-elastic-apm-java-agent)
- [Jenkins pipeline shared library for the project Elastic APM 🌟](https://github.com/elastic/apm-pipeline-library)

![Elastic APM](images/elasticapm.png)

### Dynatrace APM
* [adictosaltrabajo.com: Monitorización y análisis de rendimiento de aplicaciones con Dynatrace APM](https://www.adictosaltrabajo.com/tutoriales/monitorizacion-y-analisis-de-rendimiento-de-aplicaciones-con-dynatrace/)
* [dynatrace.com: openshift monitoring](https://www.dynatrace.com/technologies/openshift-monitoring/)
* [dynatrace.com: Dynatrace monitoring for Kubernetes and OpenShift](https://www.dynatrace.com/news/blog/dynatrace-monitoring-for-kubernetes-and-openshift/)
* [dynatrace.com: Deploy OneAgent on OpenShift Container Platform](https://www.dynatrace.com/support/help/cloud-platforms/openshift/full-stack/deploy-oneagent-on-openshift-container-platform/)
* [Successful Kubernetes Monitoring – Three Pitfalls to Avoid](https://www.dynatrace.com/news/blog/successful-kubernetes-monitoring-3-pitfalls-to-avoid/)
* [My Dynatrace proof of concept 🌟](https://github.com/redhatspain/awesome-kubernetes/blob/master/pdf/dynatrace_demo.pdf)
* [Tutorial: Guide to automated SRE-driven performance engineering 🌟](https://www.dynatrace.com/news/blog/guide-to-automated-sre-driven-performance-engineering-analysis/)
* [dynatrace.com: 4 steps to modernize your IT service operations with Dynatrace](https://www.dynatrace.com/news/blog/4-steps-to-modernize-your-it-service-operations-with-dynatrace/)
* [dynatrace.com: Monitoring of Kubernetes Infrastructure for day 2 operations](https://www.dynatrace.com/news/blog/monitoring-of-kubernetes-infrastructure-for-day-2-operations/)
* [dynatrace.com: The Power of OpenShift, The Visibility of Dynatrace](https://www.dynatrace.com/news/blog/the-power-of-openshift-the-visibility-of-dynatrace/)
* [dynatrace.com: Why conventional observability fails in Kubernetes environments—A real-world use case 🌟](https://www.dynatrace.com/news/blog/why-conventional-observability-fails-in-kubernetes-environments-a-real-world-use-case)
* [dynatrace.com: A look behind the scenes of AWS Lambda and our new Lambda monitoring extension](https://www.dynatrace.com/news/blog/a-look-behind-the-scenes-of-aws-lambda-and-our-new-lambda-monitoring-extension/)
* [dynatrace.com: Analyze all AWS data in minutes with Amazon CloudWatch Metric Streams available in Dynatrace](https://www.dynatrace.com/news/blog/amazon-cloudwatch-metric-streams-launch-partnership/)
* [dynatrace.com: New Dynatrace Operator elevates cloud-native observability for Kubernetes](https://www.dynatrace.com/news/blog/new-dynatrace-operator-elevates-cloud-native-observability-for-kubernetes/)

## Message Queue Monitoring

Messaging Solution|Monitoring Solution|URL
:-------|:-------|:-----
ActiveMQ 5.8.0+|[Dynatrace](https://www.dynatrace.com)|[ref](https://www.dynatrace.com/support/help/technology-support/application-software/other-technologies/supported-out-of-the-box/activemq/)
ActiveMQ Artemis|[Micrometer Collector](https://micrometer.io/) + Prometheus|[ref1](http://activemq.apache.org/components/artemis/documentation/latest/metrics.html), [ref2](https://micrometer.io/docs/registry/prometheus)
IBM MQ|[IBM MQ](https://github.com/ibm-messaging) Exporter for Prometheus|[ref](https://github.com/ibm-messaging/mq-metric-samples/tree/master/cmd/mq_prometheus)
Kafka|[Dynatrace](https://www.dynatrace.com)|[ref1](https://www.dynatrace.com/support/help/technology-support/application-software/other-technologies/supported-out-of-the-box/kafka/), [ref2](https://www.dynatrace.com/news/blog/introducing-kafka-process-monitoring-beta/), [ref3](https://answers.dynatrace.com/spaces/482/dynatrace-open-qa/questions/232421/dynatrace-distributed-tracing-with-kafka.html)
Kafka|[Prometheus JMX Exporter](https://github.com/prometheus/jmx_exporter)|[ref1](https://github.com/prometheus/jmx_exporter/blob/master/example_configs/zookeeper.yaml), [ref2](https://github.com/prometheus/jmx_exporter/blob/master/example_configs/kafka-2_0_0.yml), [ref3](https://github.com/prometheus/jmx_exporter/blob/master/example_configs/kafka-connect.yml), [ref4](https://strimzi.io/blog/2019/10/14/improving-prometheus-metrics/), [ref5](https://medium.com/activewizards-machine-learning-company/kafka-monitoring-with-prometheus-telegraf-and-grafana-6228fed736f1), [ref6](https://medium.com/@nblaye/exporting-kafka-jmx-metrics-to-grafana-1b9d32fe900a), [ref7](https://blog.knoldus.com/monitoring-kafka-with-prometheus-and-grafana/)
Kafka|Kafka Exporter<br/> Use [JMX Exporter](https://github.com/prometheus/jmx_exporter) to export other Kafka's metrics|[ref](https://github.com/danielqsj/kafka_exporter)
Kafka|Kafdrop – Kafka Web UI|[ref](https://github.com/obsidiandynamics/kafdrop)
Kafka|ZooNavigator: Web-based ZooKeeper UI|[ref](https://zoonavigator.elkozmon.com/)
Kafka|CMAK (Cluster Manager for Apache Kafka, previously known as Kafka Manager)|[ref](https://github.com/patelh/kafka-manager)
Kafka|Xinfra Monitor (renamed from Kafka Monitor, created by Linkedin)|[ref](https://github.com/linkedin/kafka-monitor)
Kafka|Telegraf + InfluxDB|[ref](https://www.influxdata.com/integration/kafka-telegraf-integration/)
Red Hat AMQ Broker (ActiveMQ Artemis)|Prometheus plugin for AMQ Broker<br/>To monitor the health and performance of your broker instances, you can use the **Prometheus plugin for AMQ Broker** to monitor and store broker runtime metrics. Prometheus is software built for monitoring large, scalable systems and storing historical runtime data over an extended time period. The **AMQ Broker Prometheus plugin exports the broker runtime metrics to Prometheus format**, enabling you to use Prometheus itself to visualize and run queries on the data.<br/>You can also use a graphical tool, such as **Grafana, to configure more advanced visualizations and dashboards** for the metrics that the Prometheus plugin collects.<br/>The metrics that the plugin exports to Prometheus format are listed below. A description of each metric is exported along with the metric itself.|[ref1](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/managing_amq_broker/prometheus-plugin-managing), [ref2](https://github.com/lbroudoux/openshift-cases/tree/master/jboss-amq7-custom), [ref3](https://www.openshift.com/blog/enhanced-openshift-jboss-amq-container-image-for-production)
Red Hat AMQ Streams (Kafka)|[JMX](https://www.oracle.com/java/technologies/javase/javamanagement.html), OpenTracing+Jaeger <br/>ZooKeeper, the Kafka broker, Kafka Connect, and the Kafka clients all expose management information using [Java Management Extensions (JMX)](https://www.oracle.com/java/technologies/javase/javamanagement.html). Most management information is in the form of metrics that are useful for monitoring the condition and performance of your Kafka cluster. Like other Java applications, Kafka provides this management information through managed beans or MBeans.<br/> **JMX** works at the level of the JVM (Java Virtual Machine). To obtain management information, **external tools can connect to the JVM that is running ZooKeeper, the Kafka broker, and so on.** By default, only tools on the same machine and running as the same user as the JVM are able to connect.<br/>**Distributed Tracing with Jaeger:**<br/> - Kafka Producers, Kafka Consumers, and Kafka Streams applications (referred to as Kafka clients)<br/> - MirrorMaker and Kafka Connect <br/> - Kafka Bridge|[ref1](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/using_amq_streams_on_rhel/index),[ref2](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/using_amq_streams_on_rhel/assembly-distributed-tracing-str)
Red Hat AMQ Streams Operator|AMQ Streams Operator (Prometheus & Jaeger), strimzi, jmxtrans<br/>How to monitor AMQ Streams Kafka, Zookeeper and Kafka Connect clusters using Prometheus to provide monitoring data for example Grafana dashboards.<br/>Support for distributed tracing in AMQ Streams, using **Jaeger**:<br/> - You instrument Kafka Producer, Consumer, and Streams API applications for distributed tracing using an OpenTracing client library. This involves adding instrumentation code to these clients, which monitors the execution of individual transactions in order to generate trace data.<br/>  - Distributed tracing support is built in to the Kafka Connect, MirrorMaker, and Kafka Bridge components of AMQ Streams. To configure these components for distributed tracing, you configure and update the relevant custom resources.|[ref1](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/using_amq_streams_on_openshift/assembly-metrics-setup-str), [ref2](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/using_amq_streams_on_openshift/assembly-distributed-tracing-str), [ref3 strimzi](https://operatorhub.io/operator/strimzi-kafka-operator), [ref4: **jmxtrans**](https://github.com/jmxtrans/jmxtrans), [ref5: banzai operator](https://operatorhub.io/operator/banzaicloud-kafka-operator)
Red Hat AMQ Broker Operator|Prometheus (recommended) or Jolokia REST to JMX <br/>To monitor runtime data for brokers in your deployment, use one of these approaches:<br/> - [Section 9.1, “Monitoring broker runtime data using Prometheus”](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/assembly_br-broker-monitoring_broker-ocp#assembly_br-monitoring-broker-runtime-data-using-prometheus_broker-ocp)<br/> - [Section 9.2, “Monitoring broker runtime data using JMX”](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/assembly_br-broker-monitoring_broker-ocp#proc_br-monitoring-broker_broker-ocp) <br/>In general, using Prometheus is the recommended approach. However, you might choose to use the Jolokia REST interface to JMX if a metric that you need to monitor is not exported by the Prometheus plugin. For more information about the broker runtime metrics that the Prometheus plugin exports, [see Section 9.1.1, “Overview of Prometheus metrics”](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/assembly_br-broker-monitoring_broker-ocp#con-br-overview-of-prometheus-metrics_broker-ocp)|[ref1](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/deploying-broker-on-ocp-using-operator_broker-ocp), [ref2](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/assembly_br-broker-monitoring_broker-ocp), [ref3](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/assembly_br-broker-monitoring_broker-ocp#assembly_br-monitoring-broker-runtime-data-using-prometheus_broker-ocp), [ref4](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/assembly_br-broker-monitoring_broker-ocp#proc_br-monitoring-broker_broker-ocp), [ref5](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/assembly_br-broker-monitoring_broker-ocp#con-br-overview-of-prometheus-metrics_broker-ocp)

### Red Hat AMQ 7 Broker Monitoring solutions based on Prometheus and Grafana
This is a selection of monitoring solutions suitable for RH AMQ 7 Broker based on Prometheus and Grafana:

Environment|Collector/Exporter|Details/URL
:----------|:----------------:|:--------------
RHEL|Prometheus Plugin for AMQ Broker|[ref](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/managing_amq_broker/prometheus-plugin-managing)
RHEL|Prometheus JMX Exporter|Same solution applied to ActiveMQ Artemis
OpenShift 3|Prometheus Plugin for AMQ Broker|**Grafana Dashboard not available**, [ref1](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/deploying-broker-on-ocp-using-operator_broker-ocp), [ref2](https://access.redhat.com/documentation/en-us/red_hat_amq/7.6/html/deploying_amq_broker_on_openshift/assembly_br-broker-monitoring_broker-ocp)
OpenShift 4|Prometheus Plugin for AMQ Broker|Check if Grafana Dashboard is automatically setup by Red Hat AMQ Operator
OpenShift 3|Prometheus JMX Exporter|**Grafana Dashboard not available**, [ref1](https://www.openshift.com/blog/enhanced-openshift-jboss-amq-container-image-for-production), [ref2](https://github.com/lbroudoux/openshift-cases/tree/master/jboss-amq7-custom)

## Serverless Monitoring
- [thenewstack.io: Serverless Needs More Observability Tools](https://thenewstack.io/serverless-needs-more-observability-tools/)

## Distributed Tracing in Apache Beam
- [Apache Beam](https://beam.apache.org/)
- [A Distributed Tracing Adventure in Apache Beam](http://rion.io/2020/07/04/a-distributed-tracing-adventure-in-apache-beam/)

## Krossboard Converged Kubernetes usage analytics
- [Krossboard](https://krossboard.app/) All in one single place, Krossboard tracks the usage of all your clusters over time, it helps forecast capacity scale up/down, thereby enabling you to easily anticipate and master operations costs.
- [Krossboard: A centralized usage analytics approach for multiple Kubernetes](https://itnext.io/in-search-of-converged-usage-analytics-for-multiple-managed-kubernetes-c5108cb7f0e1)

## Instana APM
- [cloudbees.com: Automated Build and Deploy Feedback Using Jenkins and Instana 🌟](https://www.cloudbees.com/blog/automated-build-deploy-feedback-using-instana)

## Monitoring Etcd
- [rancher.com: Monitor Etcd with Prometheus and Grafana using Rancher](https://rancher.com/blog/2020/monitor-etcd-prometheus-grafana-rancher)

## Zabbix
- [openshift.com: Monitoring Infrastructure Openshift 4.x Using Zabbix Operator](https://www.openshift.com/blog/monitoring-infrastructure-openshift-4.x-using-zabbix-operator)
- [openshift.com: How to Monitor Openshift 4.x with Zabbix using Prometheus - Part 2](https://www.openshift.com/blog/how-to-monitoring-openshift-4.x-with-zabbix-using-prometheus-part-2)
- [cloud.redhat.com: Monitoring Infrastructure Openshift 4.x Using Zabbix Operator](https://cloud.redhat.com/blog/monitoring-infrastructure-openshift-4.x-using-zabbix-operator)

## Other Tools
- [Netdata](https://github.com/netdata/netdata) Netdata's distributed, real-time monitoring Agent collects thousands of metrics from systems, hardware, containers, and applications with zero configuration.
- [PM2](https://github.com/Unitech/pm2) is a production process manager for Node.js applications with a built-in load balancer. It allows you to keep applications alive forever, to reload them without downtime and to facilitate common system admin tasks.
- [Huginn](https://github.com/huginn/huginn) Create agents that monitor and act on your behalf. Your agents are standing by!
- [OS Query](https://github.com/osquery/osquery) SQL powered operating system instrumentation, monitoring, and analytics.
- [Glances](https://github.com/nicolargo/glances) Glances an Eye on your system. A top/htop alternative for GNU/Linux, BSD, Mac OS and Windows operating systems. It is written in Python and uses libraries to grab information from your system. It is based on an open architecture where developers can add new plugins or exports modules.
- [TDengine](https://github.com/taosdata/TDengine) is an open-sourced big data platform under GNU AGPL v3.0, designed and optimized for the Internet of Things (IoT), Connected Cars, Industrial IoT, and IT Infrastructure and Application Monitoring.
- [stackpulse.com: Automated Kubernetes Pod Restarting Analysis with StackPulse](https://stackpulse.com/blog/automated-kubernetes-pod-restarting-analysis-with-stackpulse/)
- [Checkly](https://www.checklyhq.com/) is the API & E2E monitoring platform for the modern stack: programmable, flexible and loving JavaScript.
    - [hashicorp.com: Monitoring as Code with Terraform Cloud and Checkly](https://www.hashicorp.com/blog/monitoring-as-code-with-terraform-cloud-and-checkly)

## Other Awesome Lists
- [Awesome APM](https://github.com/antonarhipov/awesome-apm)

<center>
<iframe src="//www.slideshare.net/slideshow/embed_code/key/J1S3NyN9ZeLjh9" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/MartinEtmajer/challenges-in-a-microservices-age-monitoring-logging-and-tracing-on-red-hat-openshift" title="Challenges in a Microservices Age: Monitoring, Logging and Tracing on Red Hat OpenShift" target="_blank">Challenges in a Microservices Age: Monitoring, Logging and Tracing on Red Hat OpenShift</a> </strong> from <strong><a href="https://www.slideshare.net/MartinEtmajer" target="_blank">Martin Etmajer</a></strong> </div>

<iframe src="//www.slideshare.net/slideshow/embed_code/key/lr07J585Y86D7i" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/MartinEtmajer/monitoring-microservices-at-scale-on-openshift-67500621" title="Monitoring Microservices at Scale on OpenShift (OpenShift Commons Briefing #52)" target="_blank">Monitoring Microservices at Scale on OpenShift (OpenShift Commons Briefing #52)</a> </strong> from <strong><a href="//www.slideshare.net/MartinEtmajer" target="_blank">Martin Etmajer</a></strong> </div>

<iframe src="//www.slideshare.net/slideshow/embed_code/key/CDyLLoStp2omzE" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/PurnimaKurella/dynatrace-70789377" title="Dynatrace" target="_blank">Dynatrace</a> </strong> from <strong><a href="https://www.slideshare.net/PurnimaKurella" target="_blank">Purnima Kurella</a></strong> </div>
</center>
