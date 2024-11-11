This is project for deploying [VProfile](https://github.com/hkhcoder/vprofile-project) project using VirtualBox with Vagrant for Infrastructure as Code (IaC) and Ansible for provisioning.

# Infrastructure

1. DataBase: MariaDB on [CentOS9](https://portal.cloud.hashicorp.com/vagrant/discover/generic/centos9s)
2. MemoryCache: Memcached on [CentOS9](https://portal.cloud.hashicorp.com/vagrant/discover/generic/centos9s)
3. Message Broker: RabbitMQ on [CentOS9](https://portal.cloud.hashicorp.com/vagrant/discover/generic/centos9s)
4. Application hosting: Tomcat on [CentOS9](https://portal.cloud.hashicorp.com/vagrant/discover/generic/centos9s)
5. Load Balancer: Nginx on [Ubuntu 20.04](https://portal.cloud.hashicorp.com/vagrant/discover/ubuntu/focal64)
