
```
Your Interactive Learning Environment Bash Terminal

$
$ start.sh
Starting Kubernetes...minikube version: v1.6.2
commit: 54f28ac5d3a815d1196cd5d57d707439ee4bb392
* minikube v1.6.2 on Ubuntu 18.04
* Selecting 'none' driver from user configuration (alternates: [])
* Running on localhost (CPUs=2, Memory=2461MB, Disk=47990MB) ...
* OS release is Ubuntu 18.04.3 LTS
* Preparing Kubernetes v1.17.0 on Docker '18.09.7' ...
  - kubelet.resolv-conf=/run/systemd/resolve/resolv.conf
* Pulling images ...
* Launching Kubernetes ...
* Configuring local host environment ...
* Done! kubectl is now configured to use "minikube"
* dashboard was successfully enabled
Kubernetes Started
$ ls
Desktop
$ mkdir nflesk
$ cd nflesk/
$ vim app.py
$ vim requirements.txt
$ vim Dockerfile
$  docker build -t najibun/nflask:v1 .
Sending build context to Docker daemon  4.096kB
Step 1/6 : FROM python:2.7
2.7: Pulling from library/python
8f0fdd3eaac0: Pull complete
d918eaefd9de: Pull complete
43bf3e3107f5: Pull complete
27622921edb2: Pull complete
dcfa0aa1ae2c: Pull complete
ef6ca6913068: Pull complete
a755ea00feee: Pull complete
74b6f9ff9fd6: Pull complete
bebb4b693476: Pull complete
Digest: sha256:9517f5314968111658d229ed3038630a174e7a4f1b852bd185b70f614dffba08
Status: Downloaded newer image for python:2.7
 ---> 426ba9523d99
Step 2/6 : COPY . /app
 ---> aea1ba40c2e5
Step 3/6 : WORKDIR /app
 ---> Running in ef48a78106d8
Removing intermediate container ef48a78106d8
 ---> c90a1e7b6850
Step 4/6 : RUN pip install -r requirements.txt
 ---> Running in 86bf3a62023c
DEPRECATION: Python 2.7 will reach the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 won't be maintained after that date. A future version of pip will drop support for Python 2.7. More details about Python 2 support in pip, can be found at https://pip.pypa.io/en/latest/development/release-process/#python-2-support
Collecting flask
  Downloading https://files.pythonhosted.org/packages/9b/93/628509b8d5dc749656a9641f4caf13540e2cdec85276964ff8f43bbb1d3b/Flask-1.1.1-py2.py3-none-any.whl (94kB)
Collecting flask_restful
  Downloading https://files.pythonhosted.org/packages/17/44/6e490150ee443ca81d5f88b61bb4bbb133d44d75b0b716ebe92489508da4/Flask_RESTful-0.3.7-py2.py3-none-any.whl
Collecting itsdangerous>=0.24
  Downloading https://files.pythonhosted.org/packages/76/ae/44b03b253d6fade317f32c24d100b3b35c2239807046a4c953c7b89fa49e/itsdangerous-1.1.0-py2.py3-none-any.whl
Collecting Jinja2>=2.10.1
  Downloading https://files.pythonhosted.org/packages/65/e0/eb35e762802015cab1ccee04e8a277b03f1d8e53da3ec3106882ec42558b/Jinja2-2.10.3-py2.py3-none-any.whl (125kB)
Collecting click>=5.1
  Downloading https://files.pythonhosted.org/packages/fa/37/45185cb5abbc30d7257104c434fe0b07e5a195a6847506c074527aa599ec/Click-7.0-py2.py3-none-any.whl (81kB)
Collecting Werkzeug>=0.15
  Downloading https://files.pythonhosted.org/packages/ce/42/3aeda98f96e85fd26180534d36570e4d18108d62ae36f87694b476b83d6f/Werkzeug-0.16.0-py2.py3-none-any.whl (327kB)
Collecting aniso8601>=0.82
  Downloading https://files.pythonhosted.org/packages/eb/e4/787e104b58eadc1a710738d4e418d7e599e4e778e52cb8e5d5ef6ddd5833/aniso8601-8.0.0-py2.py3-none-any.whl (43kB)
Collecting pytz
  Downloading https://files.pythonhosted.org/packages/e7/f9/f0b53f88060247251bf481fa6ea62cd0d25bf1b11a87888e53ce5b7c8ad2/pytz-2019.3-py2.py3-none-any.whl (509kB)
Collecting six>=1.3.0
  Downloading https://files.pythonhosted.org/packages/65/26/32b8464df2a97e6dd1b656ed26b2c194606c16fe163c695a992b36c11cdf/six-1.13.0-py2.py3-none-any.whl
Collecting MarkupSafe>=0.23
  Downloading https://files.pythonhosted.org/packages/fb/40/f3adb7cf24a8012813c5edb20329eb22d5d8e2a0ecf73d21d6b85865da11/MarkupSafe-1.1.1-cp27-cp27mu-manylinux1_x86_64.whl
Installing collected packages: itsdangerous, MarkupSafe, Jinja2, click, Werkzeug, flask, aniso8601, pytz, six, flask-restful
Successfully installed Jinja2-2.10.3 MarkupSafe-1.1.1 Werkzeug-0.16.0 aniso8601-8.0.0 click-7.0 flask-1.1.1 flask-restful-0.3.7 itsdangerous-1.1.0 pytz-2019.3 six-1.13.0
Removing intermediate container 86bf3a62023c
 ---> a10ab84091f6
Step 5/6 : ENTRYPOINT ["python"]
 ---> Running in c8ffae8db188
Removing intermediate container c8ffae8db188
 ---> 531f012c3edb
Step 6/6 : CMD ["app.py"]
 ---> Running in 4172abc89248
Removing intermediate container 4172abc89248
 ---> 64619860d1bf
Successfully built 64619860d1bf
Successfully tagged najibun/nflask:v1
$ docker images | grep flask
najibun/nflask                                  v1                  64619860d1bf        8 seconds ago       903MB
$ docker login
Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.
Username: najibun
Password:
WARNING! Your password will be stored unencrypted in /root/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
$ docker push najibun/nflask:v1
The push refers to repository [docker.io/najibun/nflask]
27d89e03f5ec: Preparing
eb19432ac0ce: Preparing
27d89e03f5ec: Pushed
03a3dc679282: Mounted from library/python
35fc403d4c4c: Mounted from library/python
c1fbc35a2660: Mounted from library/python
f63773c65620: Mounted from library/python
e6d60910d056: Mounted from library/python
b52c1c103fae: Mounted from library/python
6f1c84e6ec59: Mounted from library/python
dd5242c2dc8a: Mounted from library/python
v1: digest: sha256:c8a79433e0ad5eaa5a829453e6f31a2960d395f663a98225af5a587ac27b07a8 size: 2639
$ kubectl create deployment najib-flask --image=najibun/nflask:v1
deployment.apps/najib-flask created
$ kubectl get deployments
NAME          READY   UP-TO-DATE   AVAILABLE   AGE
najib-flask   0/1     1            0           25s
$ kubectl get pods
NAME                           READY   STATUS             RESTARTS   AGE
najib-flask-86bc877644-cbwx5   0/1     CrashLoopBackOff   2          42s
$ kubectl get events
LAST SEEN   TYPE      REASON                    OBJECT                              MESSAGE
10m         Normal    NodeHasSufficientMemory   node/minikube                       Node minikube status is now: NodeHasSufficientMemory
10m         Normal    NodeHasNoDiskPressure     node/minikube                       Node minikube status is now: NodeHasNoDiskPressure
10m         Normal    NodeHasSufficientPID      node/minikube                       Node minikube status is now: NodeHasSufficientPID
10m         Normal    Starting                  node/minikube                       Starting kubelet.
10m         Normal    NodeHasSufficientMemory   node/minikube                       Node minikube status is now: NodeHasSufficientMemory
10m         Normal    NodeHasNoDiskPressure     node/minikube                       Node minikube status is now: NodeHasNoDiskPressure
10m         Normal    NodeHasSufficientPID      node/minikube                       Node minikube status is now: NodeHasSufficientPID
10m         Normal    NodeAllocatableEnforced   node/minikube                       Updated Node Allocatable limit across pods
10m         Normal    RegisteredNode            node/minikube                       Node minikube event: Registered Node minikube in Controller
10m         Normal    Starting                  node/minikube                       Starting kube-proxy.
10m         Normal    NodeReady                 node/minikube                       Node minikube status is now: NodeReady
57s         Normal    Scheduled                 pod/najib-flask-86bc877644-cbwx5    Successfully assigned default/najib-flask-86bc877644-cbwx5 to minikube
14s         Normal    Pulled                    pod/najib-flask-86bc877644-cbwx5    Container image "najibun/nflask:v1" already present on machine
14s         Normal    Created                   pod/najib-flask-86bc877644-cbwx5    Created container nflask
14s         Normal    Started                   pod/najib-flask-86bc877644-cbwx5    Started container nflask
13s         Warning   BackOff                   pod/najib-flask-86bc877644-cbwx5    Back-off restarting failed container
57s         Normal    SuccessfulCreate          replicaset/najib-flask-86bc877644   Created pod: najib-flask-86bc877644-cbwx5
57s         Normal    ScalingReplicaSet         deployment/najib-flask              Scaled up replica set najib-flask-86bc877644 to 1
$ kubectl config view
apiVersion: v1
clusters:
- cluster:
    certificate-authority: /root/.minikube/ca.crt
    server: https://172.17.0.110:8443
  name: minikube
contexts:
- context:
    cluster: minikube
    user: minikube
  name: minikube
current-context: minikube
kind: Config
preferences: {}
users:
- name: minikube
  user:
    client-certificate: /root/.minikube/client.crt
    client-key: /root/.minikube/client.key
$ kubectl expose deployment python-flask --type=LoadBalancer --port=5000
Error from server (NotFound): deployments.apps "python-flask" not found
$ kubectl expose deployment najib-flask --type=LoadBalancer --port=5000
service/najib-flask exposed
$ kubectl get services
NAME          TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes    ClusterIP      10.96.0.1      <none>        443/TCP          11m
najib-flask   LoadBalancer   10.96.112.91   <pending>     5000:32207/TCP   16s
$ kubectl get services
NAME          TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes    ClusterIP      10.96.0.1      <none>        443/TCP          13m
najib-flask   LoadBalancer   10.96.112.91   <pending>     5000:32207/TCP   2m20s
$ kubectl get events
LAST SEEN   TYPE      REASON                    OBJECT                              MESSAGE
15m         Normal    NodeHasSufficientMemory   node/minikube                       Node minikube status is now: NodeHasSufficientMemory
15m         Normal    NodeHasNoDiskPressure     node/minikube                       Node minikube status is now: NodeHasNoDiskPressure
15m         Normal    NodeHasSufficientPID      node/minikube                       Node minikube status is now: NodeHasSufficientPID
14m         Normal    Starting                  node/minikube                       Starting kubelet.
14m         Normal    NodeHasSufficientMemory   node/minikube                       Node minikube status is now: NodeHasSufficientMemory
14m         Normal    NodeHasNoDiskPressure     node/minikube                       Node minikube status is now: NodeHasNoDiskPressure
14m         Normal    NodeHasSufficientPID      node/minikube                       Node minikube status is now: NodeHasSufficientPID
14m         Normal    NodeAllocatableEnforced   node/minikube                       Updated Node Allocatable limit across pods
14m         Normal    RegisteredNode            node/minikube                       Node minikube event: Registered Node minikube in Controller
14m         Normal    Starting                  node/minikube                       Starting kube-proxy.
14m         Normal    NodeReady                 node/minikube                       Node minikube status is now: NodeReady
5m14s       Normal    Scheduled                 pod/najib-flask-86bc877644-cbwx5    Successfully assigned default/najib-flask-86bc877644-cbwx5 to minikube
3m49s       Normal    Pulled                    pod/najib-flask-86bc877644-cbwx5    Container image "najibun/nflask:v1" already present on machine
3m49s       Normal    Created                   pod/najib-flask-86bc877644-cbwx5    Created container nflask
3m49s       Normal    Started                   pod/najib-flask-86bc877644-cbwx5    Started container nflask
8s          Warning   BackOff                   pod/najib-flask-86bc877644-cbwx5    Back-off restarting failed container
5m14s       Normal    SuccessfulCreate          replicaset/najib-flask-86bc877644   Created pod: najib-flask-86bc877644-cbwx5
5m14s       Normal    ScalingReplicaSet         deployment/najib-flask              Scaled up replica set najib-flask-86bc877644 to 1
$ kubectl get services
NAME          TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes    ClusterIP      10.96.0.1      <none>        443/TCP          15m
najib-flask   LoadBalancer   10.96.112.91   <pending>     5000:32207/TCP   3m39s
$ kubectl get services
NAME          TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes    ClusterIP      10.96.0.1      <none>        443/TCP          21m
najib-flask   LoadBalancer   10.96.112.91   <pending>     5000:32207/TCP   10m
$ kubectl get services
NAME          TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes    ClusterIP      10.96.0.1      <none>        443/TCP          22m
najib-flask   LoadBalancer   10.96.112.91   <pending>     5000:32207/TCP   10m
$ kubectl create deployment python-flask --image=najibun/nflask:v1
deployment.apps/python-flask created
$ kubectl get deployments
NAME           READY   UP-TO-DATE   AVAILABLE   AGE
najib-flask    0/1     1            0           16m
python-flask   0/1     1            0           16s
$ kubectl get pods
NAME                            READY   STATUS             RESTARTS   AGE
najib-flask-86bc877644-cbwx5    0/1     CrashLoopBackOff   8          16m
python-flask-67b6d69b56-c9rrl   0/1     CrashLoopBackOff   1          29s
$ kubectl get events
LAST SEEN   TYPE      REASON                    OBJECT                               MESSAGE
27m         Normal    NodeHasSufficientMemory   node/minikube                        Node minikube status is now: NodeHasSufficientMemory
27m         Normal    NodeHasNoDiskPressure     node/minikube                        Node minikube status is now: NodeHasNoDiskPressure
27m         Normal    NodeHasSufficientPID      node/minikube                        Node minikube status is now: NodeHasSufficientPID
26m         Normal    Starting                  node/minikube                        Starting kubelet.
26m         Normal    NodeHasSufficientMemory   node/minikube                        Node minikube status is now: NodeHasSufficientMemory
26m         Normal    NodeHasNoDiskPressure     node/minikube                        Node minikube status is now: NodeHasNoDiskPressure
26m         Normal    NodeHasSufficientPID      node/minikube                        Node minikube status is now: NodeHasSufficientPID
26m         Normal    NodeAllocatableEnforced   node/minikube                        Updated Node Allocatable limit across pods
26m         Normal    RegisteredNode            node/minikube                        Node minikube event: Registered Node minikube in Controller
26m         Normal    Starting                  node/minikube                        Starting kube-proxy.
26m         Normal    NodeReady                 node/minikube                        Node minikube status is now: NodeReady
17m         Normal    Scheduled                 pod/najib-flask-86bc877644-cbwx5     Successfully assigned default/najib-flask-86bc877644-cbwx5 to minikube
15m         Normal    Pulled                    pod/najib-flask-86bc877644-cbwx5     Container image "najibun/nflask:v1" already present on machine
15m         Normal    Created                   pod/najib-flask-86bc877644-cbwx5     Created container nflask
15m         Normal    Started                   pod/najib-flask-86bc877644-cbwx5     Started container nflask
2m8s        Warning   BackOff                   pod/najib-flask-86bc877644-cbwx5     Back-off restarting failed container
17m         Normal    SuccessfulCreate          replicaset/najib-flask-86bc877644    Created pod: najib-flask-86bc877644-cbwx5
17m         Normal    ScalingReplicaSet         deployment/najib-flask               Scaled up replica set najib-flask-86bc877644 to 1
45s         Normal    Scheduled                 pod/python-flask-67b6d69b56-c9rrl    Successfully assigned default/python-flask-67b6d69b56-c9rrl to minikube
10s         Normal    Pulled                    pod/python-flask-67b6d69b56-c9rrl    Container image "najibun/nflask:v1" already present on machine
9s          Normal    Created                   pod/python-flask-67b6d69b56-c9rrl    Created container nflask
7s          Normal    Started                   pod/python-flask-67b6d69b56-c9rrl    Started container nflask
2s          Warning   BackOff                   pod/python-flask-67b6d69b56-c9rrl    Back-off restarting failed container
45s         Normal    SuccessfulCreate          replicaset/python-flask-67b6d69b56   Created pod: python-flask-67b6d69b56-c9rrl
45s         Normal    ScalingReplicaSet         deployment/python-flask              Scaled up replica set python-flask-67b6d69b56 to 1
$ kubectl config view
apiVersion: v1
clusters:
- cluster:
    certificate-authority: /root/.minikube/ca.crt
    server: https://172.17.0.110:8443
  name: minikube
contexts:
- context:
    cluster: minikube
    user: minikube
  name: minikube
current-context: minikube
kind: Config
preferences: {}
users:
- name: minikube
  user:
    client-certificate: /root/.minikube/client.crt
    client-key: /root/.minikube/client.key
$ kubectl expose deployment python-flask --type=LoadBalancer --port=5000
service/python-flask exposed
$ kubectl get services
NAME           TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes     ClusterIP      10.96.0.1      <none>        443/TCP          28m
najib-flask    LoadBalancer   10.96.112.91   <pending>     5000:32207/TCP   16m
python-flask   LoadBalancer   10.96.92.81    <pending>     5000:30540/TCP   15s
$ kubectl get services
NAME           TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes     ClusterIP      10.96.0.1      <none>        443/TCP          28m
najib-flask    LoadBalancer   10.96.112.91   <pending>     5000:32207/TCP   17m
python-flask   LoadBalancer   10.96.92.81    <pending>     5000:30540/TCP   53s
$ docker images
REPOSITORY                                      TAG                 IMAGE ID            CREATED             SIZE
najibun/nflask                                  v1                  64619860d1bf        28 minutes ago      903MB
python                                          2.7                 426ba9523d99        10 days ago         896MB
k8s.gcr.io/kube-proxy                           v1.17.0             7d54289267dc        4 weeks ago         116MB
k8s.gcr.io/kube-scheduler                       v1.17.0             78c190f736b1        4 weeks ago         94.4MB
k8s.gcr.io/kube-controller-manager              v1.17.0             5eb3b7486872        4 weeks ago         161MB
k8s.gcr.io/kube-apiserver                       v1.17.0             0cae8d5cc64c        4 weeks ago         171MB
kubernetesui/dashboard                          v2.0.0-beta8        eb51a3597525        4 weeks ago         90.8MB
redis                                           latest              dcf9ec9265e0        6 weeks ago         98.2MB
k8s.gcr.io/coredns                              1.6.5               70f311871ae1        2 months ago        41.6MB
ubuntu                                          latest              775349758637        2 months ago        64.2MB
k8s.gcr.io/etcd                                 3.4.3-0             303ce5db0e90        2 months ago        288MB
kubernetesui/metrics-scraper                    v1.0.2              3b08661dc379        2 months ago        40.1MB
alpine                                          latest              965ea09ff2eb        2 months ago        5.55MB
weaveworks/scope                                1.11.4              a082d48f0b39        5 months ago        78.5MB
k8s.gcr.io/kube-addon-manager                   v9.0.2              bd12a212f9dc        5 months ago        83.1MB
quay.io/ansible/molecule                        2.20                1171569d6ba4        9 months ago        704MB
weaveworks/scope                                1.10.2              d9ece03f45e7        10 months ago       75.8MB
k8s.gcr.io/kube-addon-manager                   v9.0                119701e77cbc        11 months ago       83.1MB
k8s.gcr.io/coredns                              1.3.1               eb516548c180        11 months ago       40.3MB
k8s.gcr.io/kubernetes-dashboard-amd64           v1.10.1             f9aed6605b81        12 months ago       122MB
k8s.gcr.io/etcd                                 3.3.10              2c4adeb21b4f        13 months ago       258MB
gcr.io/hello-minikube-zero-install/hello-node   latest              14f0c79cd094        14 months ago       655MB
gcr.io/kubernetes-helm/tiller                   v2.10.0             0cccc6576d01        16 months ago       68.9MB
k8s.gcr.io/heapster-amd64                       v1.5.3              f57c75cd7b0a        20 months ago       75.3MB
k8s.gcr.io/pause                                3.1                 da86e6ba6ca1        2 years ago         742kB
gcr.io/k8s-minikube/storage-provisioner         v1.8.1              4689081edb10        2 years ago         80.8MB
k8s.gcr.io/heapster-influxdb-amd64              v1.3.3              577260d221db        2 years ago         12.5MB
k8s.gcr.io/heapster-grafana-amd64               v4.4.3              8cb3de219af7        2 years ago         152MB
quay.io/munnerz/keepalived-cloud-provider       0.0.1               e099e9cd14a0        2 years ago         127MB
redis                                           3.0.7-alpine        856249f48b0c        2 years ago         12.6MB
gcr.io/google_containers/kube-keepalived-vip    0.9                 959a1b4b8b0f        3 years ago         142MB
jocatalin/kubernetes-bootcamp                   v2                  b6556396ebd4        3 years ago         211MB
jocatalin/kubernetes-bootcamp                   v1                  8fafd8af70e9        3 years ago         211MB
gcr.io/google-samples/kubernetes-bootcamp       v1                  8fafd8af70e9        3 years ago         211MB
gcr.io/google_containers/echoserver             1.4                 a90209bb39e3        3 years ago         140MB
gcr.io/google-samples/gb-frontend               v3                  c038466384ab        4 years ago         510MB
gcr.io/google_samples/gb-redisslave             v1                  5f026ddffa27        4 years ago         109MB
$ docker images |grep flask
najibun/nflask                                  v1                  64619860d1bf        28 minutes ago      903MB
$ kubectl get services
NAME           TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes     ClusterIP      10.96.0.1      <none>        443/TCP          35m
najib-flask    LoadBalancer   10.96.112.91   <pending>     5000:32207/TCP   23m
python-flask   LoadBalancer   10.96.92.81    <pending>     5000:30540/TCP   7m25s
$ kubctl get pods

Command 'kubctl' not found, did you mean:

  command 'kubectl' from snap kubectl (1.17.0)

See 'snap info <snapname>' for additional versions.

$ kubectl get pods
NAME                            READY   STATUS             RESTARTS   AGE
najib-flask-86bc877644-cbwx5    0/1     Error              10         26m
python-flask-67b6d69b56-c9rrl   0/1     CrashLoopBackOff   6          9m57s
$ kubectl
kubectl controls the Kubernetes cluster manager.

 Find more information at: https://kubernetes.io/docs/reference/kubectl/overview/

Basic Commands (Beginner):
  create         Create a resource from a file or from stdin.
  expose         Take a replication controller, service, deployment or pod and expose it as a new Kubernetes Service
  run            Run a particular image on the cluster
  set            Set specific features on objects

Basic Commands (Intermediate):
  explain        Documentation of resources
  get            Display one or many resources
  edit           Edit a resource on the server
  delete         Delete resources by filenames, stdin, resources and names, or by resources and label selector

Deploy Commands:
  rollout        Manage the rollout of a resource
  scale          Set a new size for a Deployment, ReplicaSet or Replication Controller
  autoscale      Auto-scale a Deployment, ReplicaSet, or ReplicationController

Cluster Management Commands:
  certificate    Modify certificate resources.
  cluster-info   Display cluster info
  top            Display Resource (CPU/Memory/Storage) usage.
  cordon         Mark node as unschedulable
  uncordon       Mark node as schedulable
  drain          Drain node in preparation for maintenance
  taint          Update the taints on one or more nodes

Troubleshooting and Debugging Commands:
  describe       Show details of a specific resource or group of resources
  logs           Print the logs for a container in a pod
  attach         Attach to a running container
  exec           Execute a command in a container
  port-forward   Forward one or more local ports to a pod
  proxy          Run a proxy to the Kubernetes API server
  cp             Copy files and directories to and from containers.
  auth           Inspect authorization

Advanced Commands:
  diff           Diff live version against would-be applied version
  apply          Apply a configuration to a resource by filename or stdin
  patch          Update field(s) of a resource using strategic merge patch
  replace        Replace a resource by filename or stdin
  wait           Experimental: Wait for a specific condition on one or many resources.
  convert        Convert config files between different API versions
  kustomize      Build a kustomization target from a directory or a remote url.

Settings Commands:
  label          Update the labels on a resource
  annotate       Update the annotations on a resource
  completion     Output shell completion code for the specified shell (bash or zsh)

Other Commands:
  api-resources  Print the supported API resources on the server
  api-versions   Print the supported API versions on the server, in the form of "group/version"
  config         Modify kubeconfig files
  plugin         Provides utilities for interacting with plugins.
  version        Print the client and server version information

Usage:
  kubectl [flags] [options]

Use "kubectl <command> --help" for more information about a given command.
Use "kubectl options" for a list of global command-line options (applies to all commands).
$ kubectl --help
kubectl controls the Kubernetes cluster manager.

 Find more information at: https://kubernetes.io/docs/reference/kubectl/overview/

Basic Commands (Beginner):
  create         Create a resource from a file or from stdin.
  expose         Take a replication controller, service, deployment or pod and expose it as a new Kubernetes Service
  run            Run a particular image on the cluster
  set            Set specific features on objects

Basic Commands (Intermediate):
  explain        Documentation of resources
  get            Display one or many resources
  edit           Edit a resource on the server
  delete         Delete resources by filenames, stdin, resources and names, or by resources and label selector

Deploy Commands:
  rollout        Manage the rollout of a resource
  scale          Set a new size for a Deployment, ReplicaSet or Replication Controller
  autoscale      Auto-scale a Deployment, ReplicaSet, or ReplicationController

Cluster Management Commands:
  certificate    Modify certificate resources.
  cluster-info   Display cluster info
  top            Display Resource (CPU/Memory/Storage) usage.
  cordon         Mark node as unschedulable
  uncordon       Mark node as schedulable
  drain          Drain node in preparation for maintenance
  taint          Update the taints on one or more nodes

Troubleshooting and Debugging Commands:
  describe       Show details of a specific resource or group of resources
  logs           Print the logs for a container in a pod
  attach         Attach to a running container
  exec           Execute a command in a container
  port-forward   Forward one or more local ports to a pod
  proxy          Run a proxy to the Kubernetes API server
  cp             Copy files and directories to and from containers.
  auth           Inspect authorization

Advanced Commands:
  diff           Diff live version against would-be applied version
  apply          Apply a configuration to a resource by filename or stdin
  patch          Update field(s) of a resource using strategic merge patch
  replace        Replace a resource by filename or stdin
  wait           Experimental: Wait for a specific condition on one or many resources.
  convert        Convert config files between different API versions
  kustomize      Build a kustomization target from a directory or a remote url.

Settings Commands:
  label          Update the labels on a resource
  annotate       Update the annotations on a resource
  completion     Output shell completion code for the specified shell (bash or zsh)

Other Commands:
  api-resources  Print the supported API resources on the server
  api-versions   Print the supported API versions on the server, in the form of "group/version"
  config         Modify kubeconfig files
  plugin         Provides utilities for interacting with plugins.
  version        Print the client and server version information

Usage:
  kubectl [flags] [options]

Use "kubectl <command> --help" for more information about a given command.
Use "kubectl options" for a list of global command-line options (applies to all commands).
$ kubectl create deployment python-flask-beda --image=lindaagustina/python-flask:v1
deployment.apps/python-flask-beda created
$ kubectl get deployments
NAME                READY   UP-TO-DATE   AVAILABLE   AGE
najib-flask         0/1     1            0           28m
python-flask        0/1     1            0           11m
python-flask-beda   0/1     1            0           15s
$ kubectl get pods
NAME                                 READY   STATUS              RESTARTS   AGE
najib-flask-86bc877644-cbwx5         0/1     CrashLoopBackOff    10         28m
python-flask-67b6d69b56-c9rrl        0/1     CrashLoopBackOff    7          11m
python-flask-beda-68cd94fc76-k9gpj   0/1     ContainerCreating   0          26s
$ kubectl get pods
^[[A\NAME                                 READY   STATUS              RESTARTS   AGE
najib-flask-86bc877644-cbwx5         0/1     CrashLoopBackOff    10         28m
python-flask-67b6d69b56-c9rrl        0/1     CrashLoopBackOff    7          12m
python-flask-beda-68cd94fc76-k9gpj   0/1     ContainerCreating   0          48s
\$kubectl get pods
NAME                                 READY   STATUS              RESTARTS   AGE
najib-flask-86bc877644-cbwx5         0/1     CrashLoopBackOff    10         29m
python-flask-67b6d69b56-c9rrl        0/1     CrashLoopBackOff    7          12m
python-flask-beda-68cd94fc76-k9gpj   0/1     ContainerCreating   0          65s
$ kubectl get pods
NAME                                 READY   STATUS              RESTARTS   AGE
najib-flask-86bc877644-cbwx5         0/1     CrashLoopBackOff    10         30m
python-flask-67b6d69b56-c9rrl        0/1     CrashLoopBackOff    7          14m
python-flask-beda-68cd94fc76-k9gpj   0/1     ContainerCreating   0          2m49s
$ kubectl get pods
NAME                                 READY   STATUS             RESTARTS   AGE
najib-flask-86bc877644-cbwx5         0/1     CrashLoopBackOff   11         34m
python-flask-67b6d69b56-c9rrl        0/1     CrashLoopBackOff   8          17m
python-flask-beda-68cd94fc76-k9gpj   1/1     Running            0          6m12s
$
```
