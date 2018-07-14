# kube-cluster-prometheus
Kubernetes cluster + MetalLB + Istio 0.7.1 + Jaeger + Bookinfo sample app + Prometheus + Grafana. This cluster demonstrates the power of Istio tracing for debugging and Prometheus/Grafana for monitoring and analytics of microservice calls.


## Requirements
* Vagrant
* Virtual Box
* Ubuntu
* IP Addresses
  - 172.16.0.40 for kubemaster
  - 172.16.0.41 for kubenode1
  - 172.16.0.41 for kubenode2
  - 172.16.0.130 to 172,16.0.150 for deployments that require LoadBalancer service type.


## Create directory
mkdir -p /data/vm/vagrant/kubernetes/01-cluster-prometheus/logs

## Vagrant setup
* Copy Vagranfile to /data/vm/vagrant/kubernetes/01-cluster-prometheus/
* vagrant up

## Validate Kubernetes Cluster
* Browse product page at http://172.16.0.131/productpage 
* Refresh pages a three times, pausing 2 seconds between refresh
* Login using user name "jason" and no password
* Refresh pages a three times, pausing 2 seconds between refresh
* Wait 30 seconds
* Visit http://172.16.0.132 and refresh screen every 10 minutes until the Service list box contains values
* Select istio-ingress from the Service list box
* Click Find Traces button.
* Visit Prometheus UI at http://172.16.0.133:9090/graph
* Visit Grafana UI at http://172.16.0.134:300 in a new browser tab
* Resize Grafana and product page browser so you can see them. 
* Log into to the product page with admin account with no password.
* Select Dashboard and then Istio Dashboard
* Select any metric while refreshing the product page. Grafana graph will change after 5 seconds.
