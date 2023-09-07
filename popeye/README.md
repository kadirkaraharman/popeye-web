## This project is a Popeye app embedded inside a Alpine image and shared volume with nginx, visulized on web, easy to check and access. 

*I did this project because basic popeye can give the report into your prometheus or s3, i don't have any of them, its cronejob and i colud'nt get the report, i can view logs but its not automated and not easy to do so.*

### What is Popeye

*Popeye is a utility that scans live Kubernetes cluster and reports potential issues with deployed resources and configurations. It sanitizes your cluster based on what's deployed and not what's sitting on disk. By scanning your cluster, it detects misconfigurations and helps you to ensure that best practices are in place, thus preventing future headaches.*

### What we need

* Kubernetes cluster or Minikube, Enable minikube ingress addons for web view
* Network connection

### Kubernetes Sources

* ClusterRole
* ConfigMap
* ClusterRoleBinding
* ServiceAccount
* Pod
* Service
* Ingress

### Why we need these resources

* ClusterRole, ClusterRoleBinding and ServiceAccount gives popeye pod to inspect and report all the k8s resources.
* ConfigMap for popeye installation inside the alpine
* Pod has 2 container one is alpine and other nginx, we know why we need alpine but nginx will publish this report on web
* Service, Ingress will expose our app over web. 

###### This project for local development if you wanna use for prod you need to change network sources like service ports ingresses and ssl certs for security reasons etc.

### For using this app.

```
git clone https://github.com/kadirkaraharman/popeye-web.git
cd popeye
kubectl create -f cluster-role.yaml
kubectl create -f configmap.yaml
kubectl create -f rolebinding.yaml
kubectl create -f service-account.yaml
kubectl create -f popeye.yaml
kubectl get pods

```
### Access

*for acces to ingress enpoint add the minikube ip into your hosts file with that domain name you set if you are using k8 cluster it will be control lane ip probly. and go to popeye-test.local at web browser.*

### Thats it after 3-5 min later popeye will produce the report and it will be visable on that domain name we set inside ingress.
