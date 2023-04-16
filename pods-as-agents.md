# **Kubernetes Pods as Jenkins Build agents**

### **Prerequisites**
 * Kubernetes cluster 1.14 or later
 * A Jenkins instance installed
 *  Plugin named kubernetes to be installed 
 *  Service account in kubernetes cluster with required permissions and role bindings
  

### **Plugin installation**  
*  `Manage Jenkins -> Manage Nodes and Clouds -> Configure Clouds -> Add a new cloud -> Kubernetes`  we can make no. of executors to zero 

* `Kubernetes URL:`
    *  for cluster details use commnad **kubectl cluster info**
* `Jenkins URL:` If the jenkins and K8s Bootstrap are oin same server default settings are ok if jenkins is running on cluster then url to be configured


* Checkout **WebSocket** then agent allows over Https rather than jenkins TCP port, This is unecessary when jenkins controller runs in same K8s cluster 

### **Kubernetes Pod Templte in Kubernete Plugin**
 * 
