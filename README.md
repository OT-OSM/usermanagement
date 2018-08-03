User n Group Management
=========
Role to manage users and groups on a system.

## Description

Configure users, group, SSH keys and administrative sudo access. The role can:

* Add and remove groups
* Add and remove users
* Install SSH keys for users
* Configure sudo to allow root access for the administration group

``` NOTE : To generate key-pair "HOST" should be localhost only as we are keeping key-pairs in our 'files' directory. ```

For ex; key_gen_path: "/etc/ansible/roles/user-mgmt/files/"

## Directory Structure
```
.
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── README.md
├── tasks
│   ├── keypair.yml
│   ├── main.yml
│   └── user.yml
├── templates
│   └── sudoers
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml
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




Role Variables
--------------

Update role variables as required in `vars/main.yml`



Playbook Execution
----------------

Execute the playbook individually using the below command with required extra variables ( for ex; playbook name: users.yml):

 ```  (To generate key_pair) : ansible-playbook users.yml -e "ENV=dev HOST=localhost" --tags "key_mgmt" ```
 
 ```  (To create users and groups) : ansible-playbook users.yml -e "ENV=dev HOST=node1" --tags "user_mgmt" ```


## Author Information


* Priyanka Sharma
* priyanka.sharma@opstree.com
(https://www.opstree.com/)

#### Feedback, bug-reports, requests, ...

* priyanka.sharma@opstree.com


