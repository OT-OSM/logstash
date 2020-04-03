Ansible Role: osm_logstash
=========

An Ansible Role to install and configure Logstash.

Version History
---------------

|**Date**| **Version**| **Description**| **Changed By** |
|----------|---------|---------------|-----------------|
|**June '15** | v.1.0 | Initial Draft | Sumit Anand |

Salient Features
----------------
* This role will check if logstash is already installed or not, if not installed, it will install on the rempte host.

Supported OS
------------
  * CentOS:7
  * CentOS:6
  * Ubuntu:14
  * Ubuntu:16
  * Ubuntu:18

 
Requirements
------------
  * JAVA 8

Dependencies
------------
  * Elastticsearch

Role Variables
--------------
|**Name**| **Default value**| **Description**|
|--|--|--|
|Node.name |Test |Name of the node|
|logstash_version |7 |Version of logstash to be installed|
|elasticSearchIp |192.168.0.225 | Ip of elasticsearch|
|elasticSearchPort |9200 |Port of elasticsearch|
|logstash_ms_heap_size |512m ||
|logstash_mx_heap_size |512m ||
|Queue_page_capacity |250mb ||
|Queue_max_bytes |512mb ||
|Http_host |0.0.0.0 |Http host to which logstash will bind|
|logstash_port |5044 |Port of the logstash from where it will receive output of beats|

Inventory
----------
An inventory should look like this:-
```ini
[logstashHost]                 
192.168.1.198    ansible_user=ubuntu   
192.168.3.201    ansible_user=opstree 
```

Example Playbook
----------------

* Here is an example playbook:-
```
- hosts: logstashHost
  become: true
  roles:
    - role: osm_logstash
```
* ansible-playbook java.yml

License
-------

BSD

Author Information
------------------

- Sumit Anand
