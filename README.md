<h1 align = "center">Kubernetes</h1>

<div align="center">  
   <img alt="GitHub repo size" src="https://img.shields.io/github/repo-size/victorpereiira/Kubernetes_DevJourney">
   <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/victorpereiira/Kubernetes_DevJourney">
</div>


<p align = "center">
    <a href="#about">About</a>   |
    <a href="#content">Content</a>   |
    <a href="#how-to-contribute">How to contribute</a>   
</p>

<!-- <p align = "center"><img height = '400' src = "https://user-images.githubusercontent.com/64560823/127571876-967811e4-8686-45b2-8140-f35f76dbc58e.gif")
><p>   -->

<div align="center">
    Translate for 
    <a href="./github/readme_pt-br.md">PT-BR</a> 
</div>


## About
🧭 Kubernetes_DevJourney from [StudyVerse](https://github.com/VictorPereiira/StudyVerse)


## Project Targets

### To do

- [ ] Create a descriptive and declarative pod.
- [ ] Create a clusterIp.

### AWS ECS Study

1. To learnig fundamentals.

## Content

### Box

- Read
   - abc
- Youtube Videos
   - abc
- Courses
   - [Alura Kubernetes I](https://www.alura.com.br/curso-online-kubernetes-pods-services-configmap)
   - [Alura Kubernets II](https://cursos.alura.com.br/course/kubernetes-deployments-volumes-escalabilidade)

### Requirements
- Docker
- Linux

- Tools
   - `kubectl`
   - `minikube`
   - `virtualbox`

### What its?

1. What is the difference between `master` and `nodes` ?
2. What is the difference between `clusterIP`, `nodePort` and `loadBalancer` ?
3. What is the difference between `x` and `y` ?
    
### How to do

1. How to work with a pod.
2. How to use clusterIP service.
3. How to use nodePort service.
. How to use loadBalancer service.
5. How to work with configMap.
6. How to use a replicaSet.

- How to work with a pod.
   - Can you use `envFrom` for get all env to configMap.

```yaml
apiVersion: v1
kind: Pod
metadata:
   name: <pod-name>
   labels:
      app: <app-name>
spec:
  containers:
    - name: <container-name>
      image: <image-id>
      ports:
         - containerPorts: <port>
      env:
         - name: "USER_NAME"
           value: "<user-name>"
         - name: "USER_GROUP"
           valueFrom:
            configMapKeyRef: 
               name: <cm-name>
               key: USER_GROU
```

- How to use clusterIP service.
   - Pod comunication.
   - Safe pod ip.

```yaml
apiVersion: v1
kind: Service
metadata:
   name: <svc-name>
spec:
   type: ClusterIP
   selector:
      app: <app-name>
   ports:
      - port: <port>
        targetPort: <pod-port>
```

- How to use nodePort service.
   - On linux access app via `internal id` not bind for localhost.
      - run `kubectl get notes -o wide` for get ip.

```yaml
apiVersion: v1
kind: Service
metadata:
   name: <svc-name>
spec:
   type: NodePort
   selector:
      app: <app-name>
   ports:
      - port: <port>
        targetPort: <pod-port>
        nodePort: <30000 - 32767>
```

- How to use loadBalancer service.

```yaml
code here...
```

- How to work with configMap.

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
   name: <cm-name>
data:
   USER_GROUP: <user-group>
```

- How to use a replicaSet.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: <rs-name>
spec:
  template:
    metadata:
      name: <pod-name>
      labels:
        app: <app-name>
    spec:
      containers:
        - name: <container-name>
          image: <image-id>
  replicas: <number-of-replicas>
  selector:
    matchLabels:
      app: <app-name>
```

### Notes

Start with
`minikube start --vm-driver=virtualbox`

Run commands
`kubectl apply -f <folder/file.yaml>`


## How to contribute
- Make a fork;
- Create a branch with your feature: `git checkout -b my-feature`;
- Commit changes: `git commit -m "feat: my new feature`;
- Make a push to your branch: `git push origin my-feature`.
  
<p>After meging your receipt request to done, you can delete a branch from yours.</p>

#
<p align = "center">
    Made by 👨🏾‍💻 
    <a href="https://github.com/VictorPereiira">VictorPereira</a>
</p>


