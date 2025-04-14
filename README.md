# Devops-task5
devops internship

Deploy and manage apps in Kubernetes (Minikube)


Requirements
------------
- Windows 10/11
- Minikube (installed via Chocolatey or manually)
- kubectl CLI
- Docker
- Git (with SSH in PATH)

Project Structure
-----------------
jenkins-on-k8s/
├── deployment.yaml
└── jenkins-service.yaml

Step-by-Step Instructions
-------------------------

1. Create Project Directory
---------------------------
Open PowerShell and run:

    mkdir jenkins-on-k8s
    cd jenkins-on-k8s

2. Create YAML Files
--------------------

jenkins-service.yaml
deployment.yaml



3. Start Minikube
-----------------

    minikube start --driver=docker

4. Apply Kubernetes Manifests
-----------------------------

    kubectl apply -f deployment.yaml
    kubectl apply -f jenkins-service.yaml

5. Check Pod and Service
------------------------

    kubectl get pods
    kubectl get svc

6. Access Jenkins UI
---------------------

    minikube service jenkins-service

Or manually open in browser:

    

Find your Minikube IP:

    minikube ip

7. Get Jenkins Admin Password
-----------------------------

    kubectl exec --stdin --tty <jenkins-pod-name> -- cat /var/jenkins_home/secrets/initialAdminPassword

Use this password in the Jenkins UI to complete the setup.


