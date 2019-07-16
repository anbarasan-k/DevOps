# Development Environment plan

For development environment, we plan to deploy the web application in an apache tomcat server within a VM provisioned by vagrant. The setup is easy to deploy and less support for availability and scalability. Apache tomcat also supports HTTPS support through self signed certificates which suits our requirement. The base OS selected for VM is Ubuntu 16.04. Vagrant also supports ansible to provisioning. We have created an ansible playbook to install Java, Apache Tomcat server in VM provisioned by vagrant

Prerequisites for deploying apache server using vagrant

- VirtualBox Version 6.0.8
- Vagrant Version 2.2.5
- Ansible Version 2.8

The above versions are latest and the host OS selected is macOS mojave 10.14. The deployment code should work in any host OS provided latest version of prerequisites' software available.

# Steps to deploy

```sh
git clone https://github.com/anbarasan-k/DevOps.git 
cd DevOps 
vagrant up
```
Access the webapp in private network: https://192.168.50.5/companyNews/

# Assumptions & Limitations:
- VM provisioned is accessible only using private network since vagrant VM is not secure with ssh keys exposed and server is provisioned with self signed certificates for SSL/TLS

The webapp can be exposed to internet by adding a public network interface in the vagrant file or set up a reverse proxy in the host machine using nginx. The playbook used with vagrant can also be deployed to AWS using cloudformation/jenkins setup. A system monitoring setup can be done by configuring diamond collector to collect system metrics and post to a graphite server/influxdb and visualization using Grafana. This has not been setup since it is out of scope.
