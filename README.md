# Istio
    Istio is a service mesh technology and it brings traffic management, telemetry and security to complex kubernetes deployments. In a nutshell Istio uses Envoy proxy to inject proxy container to every pod to implement these features. 

## Setup minikube cluster to deploy istio 
        minikube start --cpus 6 --memory 8192

## Istio Install

1. download the latest Istio package from website
    ``` shell 
        curl -L https://istio.io/downloadIstio | sh -
2. move into the directory and add /bin path to shell profile, so "istioctl" command will be available
    ``` shell
        vi .zshrc
        export PATH=/Users/ravi/istio-1.16.1/bin:$PATH ```

3. Install
    ``` shell
        istioctl install --set profile=demo -y

4. Instruct to Istio to deploy envoy sidecar container by adding namespace label to default namespace
    ``` shell    
        kubectl label namespace default istio-injection=enabled
