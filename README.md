# baremetal-ingress-example

# Prerequisits

1.- Docker

2.- K8s

3.- Ingress Controller

Note: I usually installed INGRESS using HELM

# Step:

1.- Create deployment nginx-example/nginx-deployment.yml

        kubectl create -f nginx-example/nginx-deployment.yml

2.- Create service nginx-example/nginx-service.yml

        kubectl create -f nginx-example/nginx-service.yml

3.- Create ingress resource nginx-example/nginx-ingress.yml

        Edit the value of <your-hostname> with your hostname, Example: cocodrilo-emplumado.com

        kubectl create -f nginx-example/nginx-ingress.yml

4.- Get your bare metal IP address

       Example: ifconfig eth0

5.- Edit NGINX Service

        kubectl edit svc nginx-ingress

   Add the following line below clusterIPs

        externalIPs:
        - <your-ip-address>

6.- Test your work

        http://<yout-hostname>
