{{{
  "title": "Grafana",
  "date": "10-04-2021",
  "author": "Meet Chhabra",
  "attachments": [],
  "related-products" : [],
  "contentIsHTML": false,
  "sticky": false
}}}

### Description

Grafana is a tool that a customer can deploy on their own or request from Lumen under a SOW. Grafana is an industry standard monitoring tool for k8s clusters. This can be deployed via extensions in TKG for each cluster. This provides a basic component that will manage pod, node, and cluster metrics that can be represented in a dashboard via Grafana. It can be deployed to your workload via K8’s cluster on new VM’s. Also, this is a pay per route module. 
 
TKG = Tanzu Kubernetes Grid.

To access the Grafana Dashboard, Ingress Control must be installed first.

To install Ingress control - see [Implementing Ingress Control](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-ingress-contour.html).

**NOTE**: Be sure to Configure the Grafana data values YAML file to add the PVC and StorageClass parameters. Also, add the ingress and virtual_host_fqdn. Be sure to change the name associated to the public url.

For reference – (Please change the host IP accordingly)

$ vi extensions/monitoring/grafana/grafana-data-values.yaml

![Grafana PVC](../../images/dccf/Grafanapvc.png)

#### Prerequisites for Grafana

*	Download and unpack the bundle of Tanzu Kubernetes Grid extensions. For information about where to obtain the bundle, see [Download and Unpack the Tanzu Kubernetes Grid Extensions Bundle](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-index.html#unpack-bundle).
*	Deploy a Tanzu Kubernetes Grid management cluster on vSphere.
*	Deploy a Tanzu Kubernetes cluster. The examples in this topic use a cluster named **monitoring-cluster**.
*	Install the Prometheus extension on the Tanzu Kubernetes cluster. For instructions on how to install Prometheus, see [Deploy Prometheus on Tanzu Kubernetes Clusters](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-prometheus.html).
*	Install Contour for Ingress Control on the Tanzu Kubernetes cluster. For information on installing Contour, see [Implementing Ingress Control with Contour](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-ingress-contour.html).

#### Preparing the Tanzu K8’s Cluster for Deployment

*	In a terminal, go to the folder that contains the unpacked TKG extension files such as - **tkg-extensions-v1.3.1+vmware.1/extensions**.

For Ref - cd <path>/tkg-extensions-v1.3.1+vmware.1/extensions.

You should see subfolders named **authentication**, **ingress**, **logging**, **monitoring**, **registry**, and some YAML files. Run all the commands in these procedures from this location.

*	Retrieve the **admin** credentials of the cluster.

For Ref - tanzu cluster kubeconfig, get monitoring-cluster –admin.

*	Set the context of **kubectl** to the Tanzu K8’s cluster.

For Ref - kubectl config, use-context monitoring-cluster-admin@monitoring-cluster

*	If you haven't already, install **cert-manager** on the Tanzu Kubernetes workload cluster by following the procedure in [Install Cert Manager on Workload Clusters](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-index.html#cert-mgr).

Preparing the Grafana Extension Config file - see [Grafana Extension File](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-grafana.html#prepare-the-grafana-extension-configuration-file-2).

This will also guide you if you need to customize the configuration of your Grafana extension.

**Note**: Don’t forget to change “mypassword” to the desired password. 

For Reference - 

*	cp monitoring/grafana/grafana-data-values.yaml.example monitoring/grafana/grafana-data-values.yaml
*	echo -n 'mypassword' | base64.
*	vi monitoring/grafana/grafana-data-values.yaml (change the admin_password to the output from the above command).

Deploy Grafana - [Grafana on Tanzu K8's Cluster](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.3/vmware-tanzu-kubernetes-grid-13/GUID-extensions-grafana.html#deploy).

For Reference – 

*	kubectl apply -f monitoring/grafana/namespace-role.yaml.
*	kubectl -n tanzu-system-monitoring create secret generic grafana-data-values --from-file=values.yaml=monitoring/grafana/grafana-data-values.yaml.
*	kubectl apply -f extensions/monitoring/grafana/grafana-extension.


