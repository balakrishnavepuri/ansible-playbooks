## installation link ansible
https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html


1. create user ex:- username-ansible password:-ansible (do it both ACS and nodes)
     useradd <username> or  adduser <username>
     password <give any password>
2. give sudo permissions  (do it both ACS and nodes)
    visudo
3. password authentication (do it both ACS and nodes)
   vi /etc/ssh/sshd_config
   password authentication no --> yes (ubuntu)

   #password authentication yes (centos 7)
   password authentication no

   sudo service sshd restart  

   


   ACS

$ sudo apt-get update
$ sudo apt-get install software-properties-common
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
$ sudo apt-get install ansible

sudo vi /etc/ansible/hosts
localhost

ansible -m ping all



ssh-keygen

/home/ansible/.ssh

id_rsa
id_rsa.pub

ssh-copy-id node1@<private ip of node1 or private dns of node1>
ssh-copy-id node2@<private ip of node2 or private dns of node2>

ssh <private ip of node 1 or node2>

Node-1

install python

Node-2

install python

---------------------------------------

to create multiple nodes take node image of specific OS


------------------------------------

YAML(yet another markup language) 
     
     - data representation language
     - easy to read and write
     - its not programming or markup language
     - structured
     - used in ansible, kubernetes


starts with --- (play)
key:value
key:
- value1
- value2
- value3

hosts- where yo want to apply this PlayBook

- hosts: all or specify any server name

become- to become sudo user

 become: yes

--------------------------------------------------------------------

Module - utility which actually does the work
       - idempotent

1. Ping

    ping:

2. apt
  
  apt:
    name: description of package
    state: present/absent

3. yum
  
 yum:
   name: description of package 
   state: present/absent