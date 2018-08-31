User n Group Management
=========
Role to manage users and groups on a system.

## Description

Configure users, group, SSH keys and administrative sudo access. The role can:

* Add and remove groups
* Add and remove users
* Install SSH keys for users
* Configure sudo to allow root access for the administration group



## Directory Structure

```
osm_usermanagement/
├── defaults
│   └── main.yml
├── files
│   ├── add_userlist
│   └── pub_keys
│       └── rachit
├── meta
│   └── main.yml
├── README.md
├── tasks
│   ├── add_users_groups.yml
│   └── main.yml
├── templates
│   └── sudoersfile
└── users.yml

```


Supported OS
------------

```
This role will work on the following operating systems:

   * Centos 6/7
   * Debian 14/16
   * Redhat 6/7
   * Amazon AMI
```

## Requirements

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

    - hosts: '{{ HOST }}'
      roles:
        - { role: user-mgmt } 
          become: yes


Playbook Execution
----------------

 
 ```  (To create users and groups) : ansible-playbook users.yml -e " HOST=test" --tags "add_user" ```


## Author Information


* Priyanka Sharma
* priyanka.sharma@opstree.com
(https://www.opstree.com/)

#### Feedback, bug-reports, requests, ...

* priyanka.sharma@opstree.com


