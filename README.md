User n Group Management
=========
Role to manage users and groups on a system.

## Description

Configure users, group, SSH keys and administrative sudo access. The role can:

* Add groups
* Add and remove users
* Install SSH keys for users
* Configure sudo to allow root access for the administration group

Supported OS
------------

```
This role will work on the following operating systems:

   * Centos 6/7
   * Debian 14/16
   * Redhat 6/7
   * Amazon AMI
```
## Directory Structure
```
osm_usermanagement/
├── meta
│   └── main.yml
├── pub_keys
├── README.md
├── tasks
│   ├── add_users_groups.yml
│   └── main.yml
├── templates
│   └── sudoersfile
└── userlist
```
## Requirements

* This role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

```
    - hosts: '{{ HOST }}'
      roles:
        - { role: osm_usermanagement } 
      become: yes
```

* There should be a meta file for user and group details in directory structure for ex; userlist is a meta file where details should go in following format

  ```
  user1:group1:present
  
  ```

* There should be public key of all users in directory structure and it should be defined under pub_keys.Public key name would be on the name of the user.Different name would not work here. 

   ```
   For Ex; pub_keys/user1
   
   ```
   
Playbook Execution
----------------

 ```  (To create users and groups) : ansible-playbook users.yml -e " HOST=host_name" ```

## Author Information

* Priyanka Sharma
* priyanka.sharma@opstree.com
(https://www.opstree.com/)

#### Feedback, bug-reports, requests, ...

* priyanka.sharma@opstree.com

