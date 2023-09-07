## This project is a Popeye app embedded inside a Alpine image and shared volume with nginx, visulized on web, easy to check and access. 

*I did this project because basic popeye can give the report into your prometheus or s3, i don't have any of them, its cronejob and i colud'nt get the report, i can view logs but its not automated and not easy to do so.*

### What is Popeye

*Popeye is a utility that scans live Kubernetes cluster and reports potential issues with deployed resources and configurations. It sanitizes your cluster based on what's deployed and not what's sitting on disk. By scanning your cluster, it detects misconfigurations and helps you to ensure that best practices are in place, thus preventing future headaches.*

### What we need

* Kubernetes cluster or Minikube, Enable minikube ingress addons for web view
* Network connection

### Kubernetes Sources

* Cluster Role
* Configmap
* RoleBinding
* ServiceAccount
* Pod