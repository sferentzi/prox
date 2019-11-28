- [ ] !!! search for prox!!!
# project *prox*

# ToDo's

## Create repo @ GitHubb
- [ ] !! write the rest

## Setting up VMs (manually)
- Install Linux centOS 7 on each VM-s
- Set IP-s and Hostnames, as follows:
 - VM 1 setting: 192.168.56.30, ansible-controller, (0)
 - VM 2 setting: 192.168.56.31, ansible-web, (A)
 - VM 3 setting: 192.168.56.32, ansible-nodejs, (B)
 - root / 000000

 ## --> Do Snapshot 1
 - - [x] Snapshot 1 @ All

## Log in to *ansible-controller* as *root*
- [ ] ??? Should we test Python version? (python --version)
### Install & check Ansible manually
~~~
yum install ansible
ansible --version
~~~

### Install Git manually
- [ ] ??? Is it ok, to install Git on (0) manually?
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

### Make fingerprints as *root* to *web* and *nodejs* (break with ctrl + c)
~~~
ssh 129.168.56.31 -l root
ssh 129.168.56.32 -l root 
~~~

### --> Do Snapshot 2
- [x] Snapshot 2 @ Controller

## Add Fingerprint from your Local computer *ansible-controller* as *exam*
~~~
ssh 129.168.56.31 -l exam
~~~

## Open your favourite IDE and log in to *ansible-controller* as *exam*
- Navigate to ~(home) folder (/home/exam)

### Set Git global variables for Git user & check it
~~~
git config --global user.name "Sandor Ferentzi"
git config --global user.email "sandor.ferentzi@gmail.com"
git config --global user.name
git config --global user.email
~~~

### Clone remote Git repository *ansible_docker_exam* and enter folder
- [ ] Change repo name and folder name !!!
~~~
git clone https://github.com/sferentzi/prox.git
cd prox
~~~

### --> Do Snapshot 3
- [ ] Do Snapshot @ All VM

### Generate ssh-key
~~~
ssh-keygen
~~~

### Create *init_hosts* file
- place to /home/exam/prox

### Create *init_users.yaml* file
- place to /home/exam/prox

### Change to user *root*
~~~
sudo su
~~~

### Run the playbook to init users on the *hosts*
- Hint: you shuold be now root@ansible-controller
- [ ] ??? Do we need to validate? (2x)
~~~
ansible-playbook -i init_hosts init_users.yaml -k
~~~

### Change back to user *exam*
- Hint: press ctrl + d

### Make fingerprints as *exam* to *web* and *nodejs*
~~~
ssh 129.168.56.31 -l exam
ssh 129.168.56.32 -l exam 
~~~

### --> Do Snapshot 4
- [ ] Do Snapshot 4 @ All VM

## Set Up apache & nodejs

### Create host file run_hosts
- Place it to /home/exam/prox

### Create yaml file run.yaml
- [ ] ??? become:true needed ???
- [ ] !!! make httpd idempotent
- [ ] !!! enable httpd by systemctl
- [ ] !!! Set Apache proxy
- Place it to /home/exam/prox
- --> Do Snapshot 5, if apache is running
- [ ] Do Snapshot 5 @ All VM