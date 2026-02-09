# binoculars
Basic observability using ELK or EFK , Prometheus and Grafana


Prerequisites:
1. To have a kubernetes cluster that has access to internet.
2. To install helm 3 - https://helm.sh/docs/v3/intro/install.
3. Deploy a Petclinic Sprintboot petclinic application.

Obervbility tools installation:
ELASTICSEARCH - 
helm repo add elastic https://helm.elastic.co
helm install my-elasticsearch elastic/elasticsearch --version 8.5.1

FluentD - 
helm repo add fluent https://fluent.github.io/helm-charts
helm install my-fluentd fluent/fluentd --version 0.5.3

Kibana - 
helm repo add elastic https://helm.elastic.co
helm install my-kibana elastic/kibana --version 8.5.1

Prometheus - 
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install my-prometheus prometheus-community/prometheus --version 28.9.0

Grafana - 
helm repo add grafana-community https://grafana-community.github.io/helm-charts/
helm install my-grafana grafana-community/grafana --version 11.0.1


Configuration:
Configure the Elastic, fluentD in such a way that it starts fetching the logs from the cluster and the Petclinic App Pod and is visbile in Kibana.
Configure the Prometheus in such a way that it starts fetching the metrices from the cluster and the Petclinic App Pod and is visible in Grafana.