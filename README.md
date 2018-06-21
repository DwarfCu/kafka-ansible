# kafka-ansible
## Installation
### VirtualBox​​
1) Visit https://www.virtualbox.org/wiki/Linux_Downloads
2) Download and install ej. Ubuntu 16.04 AMD64
3) Run:
```
virtualbox -h
Oracle VM VirtualBox Manager 5.2.12
...
```
### Vagrant
1) ​Visit ​https://releases.hashicorp.com/vagrant/
2) Download ​and install ej. ​vagrant_2.1.1_x86_64.deb
​3) Run:
```
vagrant -v
​​​Vagrant 2.1.1
```
### Ansible
```
sudo apt-add-repository -y ppa:ansible/ansible
sudo apt-get update
sudo apt-get install -y ansible
​ansible --version​
​ansible 2.5.4
...
```
### GitHub: kafka-ansible
```
git clone https://github.com/DwarfCu/kafka-ansible.git
```
## Run environment
```
vagrant up
```
Test SSH access (CLI):
```
ssh -p 2222 vagrant@127.0.0.1 -i .vagrant/machines/vlikfk01/virtualbox/private_key
```
```
​vagrant@vlikfk01$ exit​
```
Edit hosts configuration (if neccesary):
```
vim kafka-hosts
​​vlikfk01 ansible_host=127.0.0.1 ansible_ssh_port=2222 ansible_user=vagrant ansible_ssh_private_key_file=.vagrant/machines/vlikfk01/virtualbox/private_key
vlikfk02 ansible_host=127.0.0.1 ansible_ssh_port=2200 ansible_user=vagrant ansible_ssh_private_key_file=.vagrant/machines/vlikfk02/virtualbox/private_key
vlikfk03 ansible_host=127.0.0.1 ansible_ssh_port=2201 ansible_user=vagrant ansible_ssh_private_key_file=.vagrant/machines/vlikfk03/virtualbox/private_key

[kafka_broker_nodes]
vlikfk[01:03]
```
Test SSH access (ansible):
```
ansible all -m ping -i kafka-hosts
```
Output:
```
vlikfk01 | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}
vlikfk02 | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}
vlikfk03 | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}
```
