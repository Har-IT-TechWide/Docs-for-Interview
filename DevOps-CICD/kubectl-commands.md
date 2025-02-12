Here are some essential **kubectl** commands with descriptions for managing Kubernetes clusters:  

---

### **1. Cluster Information**
| Command | Description |
|---------|------------|
| `kubectl cluster-info` | Shows cluster details, including API server and other components. |
| `kubectl get nodes` | Lists all nodes in the cluster. |
| `kubectl describe node <node-name>` | Shows detailed information about a specific node. |
| `kubectl top nodes` | Displays CPU and memory usage of nodes. |

---

### **2. Managing Namespaces**
| Command | Description |
|---------|------------|
| `kubectl get namespaces` | Lists all namespaces in the cluster. |
| `kubectl create namespace <namespace>` | Creates a new namespace. |
| `kubectl delete namespace <namespace>` | Deletes a namespace and all its resources. |
| `kubectl config set-context --current --namespace=<namespace>` | Sets the default namespace for all commands. |

---

### **3. Working with Pods**
| Command | Description |
|---------|------------|
| `kubectl get pods` | Lists all pods in the current namespace. |
| `kubectl get pods -n <namespace>` | Lists all pods in a specific namespace. |
| `kubectl describe pod <pod-name>` | Shows detailed information about a pod. |
| `kubectl logs <pod-name>` | Fetches logs of a pod’s main container. |
| `kubectl logs -f <pod-name>` | Streams live logs from a pod. |
| `kubectl exec -it <pod-name> -- /bin/bash` | Opens an interactive shell in a running pod. |
| `kubectl delete pod <pod-name>` | Deletes a specific pod. |

---

### **4. Working with Deployments**
| Command | Description |
|---------|------------|
| `kubectl get deployments` | Lists all deployments. |
| `kubectl describe deployment <deployment-name>` | Shows details of a deployment. |
| `kubectl scale deployment <deployment-name> --replicas=3` | Scales a deployment to 3 replicas. |
| `kubectl rollout restart deployment <deployment-name>` | Restarts a deployment. |
| `kubectl rollout history deployment <deployment-name>` | Shows the rollout history of a deployment. |
| `kubectl delete deployment <deployment-name>` | Deletes a deployment. |

---

### **5. Managing Services**
| Command | Description |
|---------|------------|
| `kubectl get services` | Lists all services. |
| `kubectl describe service <service-name>` | Shows details of a service. |
| `kubectl expose deployment <deployment-name> --type=LoadBalancer --port=80` | Exposes a deployment as a service. |
| `kubectl delete service <service-name>` | Deletes a service. |

---

### **6. Working with ConfigMaps and Secrets**
| Command | Description |
|---------|------------|
| `kubectl get configmaps` | Lists all ConfigMaps. |
| `kubectl describe configmap <configmap-name>` | Shows details of a ConfigMap. |
| `kubectl create configmap my-config --from-literal=key=value` | Creates a ConfigMap from key-value pairs. |
| `kubectl get secrets` | Lists all Secrets. |
| `kubectl describe secret <secret-name>` | Shows details of a Secret. |
| `kubectl create secret generic my-secret --from-literal=username=admin` | Creates a Secret with a key-value pair. |

---

### **7. Working with Ingress**
| Command | Description |
|---------|------------|
| `kubectl get ingress` | Lists all Ingress resources. |
| `kubectl describe ingress <ingress-name>` | Shows details of an Ingress. |
| `kubectl delete ingress <ingress-name>` | Deletes an Ingress resource. |

---

### **8. Managing Persistent Volumes**
| Command | Description |
|---------|------------|
| `kubectl get pv` | Lists all Persistent Volumes (PVs). |
| `kubectl get pvc` | Lists all Persistent Volume Claims (PVCs). |
| `kubectl describe pvc <pvc-name>` | Shows details of a PVC. |
| `kubectl delete pvc <pvc-name>` | Deletes a PVC. |

---

### **9. Debugging & Troubleshooting**
| Command | Description |
|---------|------------|
| `kubectl get events` | Lists recent cluster events. |
| `kubectl get pods --field-selector=status.phase=Running` | Shows only running pods. |
| `kubectl describe pod <pod-name>` | Shows pod details, including errors. |
| `kubectl logs <pod-name>` | Fetches logs of a pod. |
| `kubectl exec -it <pod-name> -- /bin/sh` | Opens a shell in a running container. |
| `kubectl get all` | Lists all resources in the namespace. |

---

### **10. Managing Roles & RBAC**
| Command | Description |
|---------|------------|
| `kubectl get roles` | Lists all roles in the namespace. |
| `kubectl get rolebindings` | Lists all role bindings. |
| `kubectl describe role <role-name>` | Shows details of a role. |

---

### **11. Miscellaneous Commands**
| Command | Description |
|---------|------------|
| `kubectl api-resources` | Lists all Kubernetes resources and their API versions. |
| `kubectl explain pod` | Shows documentation for pod configuration. |
| `kubectl version` | Displays the installed client and server version. |

---

### **Summary**
These **kubectl** commands will help you manage Kubernetes clusters efficiently, covering:
✅ **Cluster management**  
✅ **Pods, Deployments, Services**  
✅ **Networking (Ingress, Load Balancing)**  
✅ **ConfigMaps, Secrets, and Storage**  
✅ **Debugging and Security**  

Would you like hands-on examples or specific commands for your use case? 🚀