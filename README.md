# nginx-ingress-sample
Sample app using nginx-ingress controller

## Usage

1. [Install kubernetes using Kubespray](https://github.com/kubernetes-sigs/kubespray)

2. [Install metalLB (Load Balancer)](https://github.com/invaleed/metalLB)

3. Install NGINX Ingress Controller

```bash
$ helm install nginx-ingress stable/nginx-ingress --set rbac.create=true
```

4. Deploy sample application

```bash
$ git clone https://github.com/invaleed/nginx-ingress-sample.git
$ cd nginx-ingress-sample
$ kubectl apply -f cafe/
$ kubectl apply -f nginx-hello/

$ kubectl get ingress
NAME              CLASS    HOSTS         ADDRESS          PORTS   AGE
cafe-ingress      <none>   example.com   192.168.65.202   80      48m
hello-ingress     <none>   example.com   192.168.65.202   80      22m
```

5. Done
