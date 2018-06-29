# kafka-ansible
Automatic deployment (Vagrant) and configuration (Ansible) of a Zookeeper and Kafka cluster (3 nodes).
## Installation
### VirtualBox​​
1) Visit https://www.virtualbox.org/wiki/Linux_Downloads
2) Download and install ej. Ubuntu 16.04 AMD64
3) Run:
```
# virtualbox -h
Oracle VM VirtualBox Manager 5.2.12
...
```
### Vagrant
1) ​Visit ​https://releases.hashicorp.com/vagrant/
2) Download ​and install ej. ​vagrant_2.1.1_x86_64.deb
3) Run:
```
# vagrant -v
​​​Vagrant 2.1.1
```
### Ansible
```
# sudo apt-add-repository -y ppa:ansible/ansible
# sudo apt-get update
# sudo apt-get install -y ansible
# ​ansible --version​
​ansible 2.5.4
...
```
### GitHub: kafka-ansible
```
# git clone https://github.com/DwarfCu/kafka-ansible.git
```
## Environment
```
# cd kafka-ansible
# vagrant up
# ansible-playbook -i production site.yml
```
Send messages to topic:
```
curl "message" -u kafka:k4fk4 http://127.0.0.1:8081
```

Destroy environment:
```
# vagrant destroy
```