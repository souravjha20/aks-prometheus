Monitor your Azure Kubernetes Cluster (AKS) with Prometheus and Grafana

We will go through the Open Source options available for monitoring Azure Kubernetes Service (AKS) clusters. We will have a closer look at the Open Source tool kit widely used by the Kubernetes Community: Prometheus, and how it can be used and deployed on the clusters 

The following will be covered:
 Deploying and configuring the Prometheus stack using Helm Charts and the rometheus Operator

Pre requisites:
1. Azure subscription
2. A zure CLI
3. Basic knowledge of Kubernetes commands and components
4. An AKS cluster provisioned and is in Running state
o az aks get credentials g {resource group} n {aks cluster name}
5. Install Helm for your respective OS https://github.com/helm/helm/releases

Prometheus and Grafana are open source monitoring tools for Kubernetes clusters.It allows users and developers to capture metrics and telemetry data for applications running inside the cluster, allowing deeper insights into application performance and reliability at the container level.

Introduction to Prometheus
Prometheus is an open source system monitoring and alerting toolkit originally built at SoundCloud.Prometheus has been adopted since its inception, by many companies and
organizations, and the project has a very active developer and user community. It is now a standalone open source project and maintained independently of any company.

Prometheus joined the Cloud Native Computing Foundation in 2016 as the second Prometheus joined the Cloud Native Computing Foundation in 2016 as the second hosted project, after Kubernetes.hosted project, after Kubernetes. Prometheus provides a set of applications which collect monitoring data from youPrometheus provides a set of applications which collect monitoring data from your r applications, applications, containers,containers, and nodes by scraping a specific endpoint. These services and nodes by scraping a specific endpoint. These services collate this data and provide a way to query and alert on the data.collate this data and provide a way to query and alert on the data. In addition to the applications to collect monitoring data, Prometheus provides an In addition to the applications to collect monitoring data, Prometheus provides an easy way for you toeasy way for you to expose metrics from your own applications using a set of client expose metrics from your own applications using a set of client libraries and a libraries and a standardizedstandardized format for presenting the metrics.format for presenting the metrics. Prometheus does Prometheus does not Provide a dashboard, it relies on Grafana for visualizing data.not Provide a dashboard, it relies on Grafana for visualizing data. 

Prometheus Components

Prometheus Operator

In late 2016, CoreOS introduced the Operator pattern and released the Prometheus Operator as a working example of the pattern.The Prometheus Operator is simple to install with a single command line and enables the configuration and management of Prometh eus instances using simple declarative configuration that will, in response, create, configure, and manage Prometheus monitoring instances.

The Operator deploys the following components into the cluster:

 Prometheus, which defines a desired Prometheus deployment. The Operator always ensures that a deployment matching the resource definition is running.

 Service Monitor , which declaratively specifies how groups of services should be monitored. The Operator automatically generates Prometheus scrape configuration based on the definition.

 Alertmanager , which defines a desired Alertmanager deployment. The Operator always ensures that a deployment matching the resource definition is running.It is u sed to aggregate alerts and send them to customly configured receivers.These receivers can be: Webhooks for systems like Slack , Microsoft SMTP emailing system.

Grafana
Grafana is used to visualize any data. It ca n be used to create multiple dashboards that support a variety of beautiful graphs and visualizations for different users and
stakeholders. It has support for the integration different type of data sources like Prometheus, Azure M onitor, E lasticsearch, AWS Cloud Watch etc.
Grafana , it is u sed to visualize the metrics collected by Prometheus and exposes them on prebuilt Dashboards.
