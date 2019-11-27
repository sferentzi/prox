# project *prox*

# ToDo's

## Setting up VMs (manually)
- Install Linux centOS 7 on each VM-s
- Set IP-s and Hostnames, as follows:
 - VM 1 setting: 192.168.56.30, ansible-controller, (0)
 - VM 2 setting: 192.168.56.31, ansible-web, (A)
 - VM 3 setting: 192.168.56.32, ansible-nodejs, (B)
 - root / 000000
 - - [x] Snapshot 1 @ All

## Log in to *ansible-controller* as *root*
- [ ] ??? Should we test Python version? (python --version)
### Install & check Ansible manually
~~~
yum install ansible
ansible --version
~~~

### Install Git manually
- [ ] Is it ok, to install Git on (0) manually?
~~~
yum install git -y
~~~

### Add user exam & set password to 000000
~~~
useradd exam
passwd exam
~~~

### Add user exam to sudoers
~~~
sudo visudo
append line: 
exam ALL=(ALL) NOPASSWD:ALL
~~~

- - [x] Snapshot 1 @ Controller