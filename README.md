# ansible-tomcat

## Introduction

The scope of this playbook is to Install and Setup Tomcat V-8.X.X on Centos/7 using openjdk-1.8-devel from yum repository.


## Prerequisites
Edit the group_vars/tomcat file to Declare the required parameters first.
```
vim group_vars/tomcat
```


### Step 1
Have you configured a ssh keypair across you master and hosts for a user with sudo on nodes where this playbook will run?

The remote user on the node will need to become sudo in order for the tasks invoke successfully.

### Step 2
Have you modified the site.yml in present working dir to perform as a specific user and to which environments (hosts) to run the playbook?

### Step 3
This will dry run your playbook against the Hosts for Syntax checking

```
ansible-playbook site.yml -C 
```

### Final Step

Check of tomcat.service status is loaded in systemd 

```
systemctl status tomcat.service
```

Check if tomcat (java) is Listening on 8080 using Netstat.

```
netstat -anp | grep 8080
```

## Relax, Have Fun and Keep Automating :)
