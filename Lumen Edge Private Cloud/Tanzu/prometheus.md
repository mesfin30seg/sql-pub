{{{
  "title": "Prometheus",
  "date": "10-04-2021",
  "author": "Meet Chhabra",
  "attachments": [],
  "related-products" : [],
  "contentIsHTML": false,
  "sticky": false
}}}
  
###  Description 
  
  
Prometheus is a tool that a customer can deploy on their own or request from Lumen under a SOW. Prometheus is an industry standard monitoring tool for k8s clusters. This can be deployed via extensions in TKG for each cluster. This provides a basic component that will manage pod, node, and cluster metrics that can be represented in a dashboard. It can be deployed to your workload via the K8’s cluster on new VM’s. Also, this is a pay per route module. 
  
TKG = Tanzu Kubernetes Grid.
  
To access the Prometheus Dashboard, Ingress Control must be installed first. 
  
To install Ingress control - click [Implementing Ingress Control.](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-ingress-contour.html )
  
**NOTE**: Be sure to Configure the Prometheus data values YAML file to add the PVC and StorageClass parameters.
  
####  Prerequisites for Prometheus
  
  
* Download and unpack the bundle of Tanzu Kubernetes Grid extensions. For information on how to obtain the bundle, see [Download and Unpack the Tanzu Kubernetes Grid Extensions Bundle](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-index.html#unpack-bundle ).
  
* Make sure to find the IP and DNS record for Prometheus.
* Deploy a Tanzu Kubernetes Grid management cluster on vSphere, Amazon EC2, or Azure.
* Deploy a Tanzu Kubernetes cluster.
  
####  Preparing the Tanzu K8’s Cluster for deployment
  
  
* In a terminal, go to the folder that contains the unpacked TKG extension files, such as - **tkg-extensions-v1.3.1+vmware.1/extensions**.
  
For Ref - cd <path>/tkg-extensions-v1.3.1+vmware.1/extensions.
  
You should see subfolders named **authentication**, **ingress**, **logging**, **monitoring**, **registry**, and some YAML files. Run all the commands in these procedures from this location.
  
* Retrieve the **admin** credentials of the cluster.
  
For Ref - tanzu cluster kubeconfig get monitoring-cluster –admin.
  
* Set the context of **kubectl** to the cluster.
  
For Ref - kubectl config use-context monitoring-cluster-admin@monitoring-cluster.
  
* If you haven't already, install **cert-manager** on the Tanzu Kubernetes workload cluster by following the procedure in [Install Cert Manager on Workload Clusters](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-index.html#cert-mgr ).
  
* Create a namespace for the Prometheus service on the Tanzu Kubernetes cluster.
  
For Ref - kubectl apply -f monitoring/prometheus/namespace-role.yaml.
  
After this, you should be able to see a confirmation that a Tanzu – system- monitoring has been created.
  
For Ref - namespace/tanzu-system-monitoring created
/serviceaccount/prometheus-extension-sa created
/role.rbac.authorization.k8s.io/prometheus-extension-role created
/rolebinding.rbac.authorization.k8s.io/prometheus-extension-rolebinding created
/clusterrole.rbac.authorization.k8s.io/prometheus-extension-cluster-role created
/clusterrolebinding.rbac.authorization.k8s.io/prometheus-extension-cluster-rolebinding created. 
  
When all the pods are ready, the Tanzu K8s cluster is ready for you to deploy the Prometheus extension. 
  
Follow the procedure in preparing the Prometheus Configurations files - [Preparing Prometheus Config Files](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-prometheus.html#config ).
  
**Note**: Add the PVC and StorageClass parameters like the example below. Be sure to change the name associated to your vsan storage policy. **TIP**: vim will allow for proper formatting/tabbing of the YAML file. 

$ cp monitoring/prometheus/prometheus-data-values.yaml.
example monitoring/prometheus/prometheus-data-values.yaml

$ vim monitoring/prometheus/prometheus-data-values.yaml
  
![Alert Manager](../../images/dccf/AlertManagerTerminal.png)
  
$ cd monitoring/prometheus

$ kubectl create secret generic prometheus-data-values --from-file=values.yaml=prometheus-data-values.yaml -n tanzu-system-monitoring

$ kubectl get secrets -n tanzu-system-monitoring

$ kubectl apply -f prometheus-extension.yaml
  
For more information please refer here - [Documentation for Prometheus](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-prometheus.html).
  