# Kubernetes-Practice
This repository holding all the code which I am going to practice to learn kubernetes

# Commands:
kubectl version

minikube status

minikube update-context

minikube start

kubectl get <object> => kubectl get pods

kubectl describe <object> <object name> => kubectl describe pod testpod

kubectl apply -f file.yml

kubectl get <object> -o wide

kubectl describe <object>/<object name> => kubectl describe pod/testpod

kubectl logs -f <pod-name> => kubectl logs -f testpod

kubectl logs -f <pod-name> -c <container name> => kubectl logs -f testpod -c c00

kubectl delete <object> <object name>

kubectl delete -f file.yml

kubectl exec <podname> -c <container name> -- <Command to execute> => kubectl exec testpod -c c00 -- hostname

kubectl exec -it <podname> -c <container name> -- /bin/bash => kubectl exec -it testpod -c c00 -- /bin/bash

kubectl exec -it <podname> -c <container name> -- /bin/sh => kubectl exec -it testpod -c c00 -- /bin/sh

