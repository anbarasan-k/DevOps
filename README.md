# DevOps

Steps to setup environment

git clone https://github.com/anbarasan-k/DevOps.git
cd DevOps
vagrant up

Access the webapp in private network: https://192.168.50.5/companyNews/

Assumptions & Limitations:

1. VM provisioned is accessible only using private network since vagrant VM is not secure with ssh keys exposed and server is provisioned with self signed certificates for SSL/TLS
