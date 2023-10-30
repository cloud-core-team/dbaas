# Prerequisites

1) Install Docker Desktop: https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module
2) Install minikube: https://github.com/kubernetes/minikube/releases/latest/download/minikube-installer.exe

# Steps

1) Run Docker Desktop;
2) Open console as Administrator;
3) Run command: 'minikube start'
4) Run command: 'minikube dashboard'. Kubernetes dashboard will be opened in your browser;
5) Run maven steps 'clean' + 'package' on our project and wait for build;
6) Open dbaas-project in console (you can just open IntelliJ Idea console, you will be already in root folder of project);
7) Run command: 'docker build . -t cloudcoreteam2023/dbaas:latest'. This command will build our project as docker-image;
8) Run command: 'docker push cloudcoreteam2023/dbaas:latest'. This command will push this image to our docker-hub;
9) Open your browser with kubernetes dashboard opened;
10) At the right upper corner of your screen you can find "BIG PLUS" button. Click on it. You will see window with big text field;
11) Put next text from [Deployment.yaml](..%2Fdeployments%2Fcharts%2Fdbaas%2Ftemplates%2FDeployment.yaml) to this field and click "Create";
12) Repeat action for two other files: [Service.yaml](..%2Fdeployments%2Fcharts%2Fdbaas%2Ftemplates%2FService.yaml) and [Ingress.yaml](..%2Fdeployments%2Fcharts%2Fdbaas%2Ftemplates%2FIngress.yaml);
13) Check on "Pods" tab that 'dbaas-****' pod has status 'Running'.