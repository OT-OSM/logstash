Ansible Role: osm_logstash
=========

[![Opstree Solutions][opstree_avatar]][opstree_homepage]<br/>[Opstree Solutions][opstree_homepage] 
  [opstree_homepage]: https://opstree.github.io/
  [opstree_avatar]: https://img.cloudposse.com/150x150/https://github.com/opstree.png

An Ansible Role to install and configure Logstash.

Version History
---------------

|**Date**| **Version**| **Description**| **Changed By** |
|----------|---------|---------------|-----------------|
|**15-June-2019** | v.1.0 | Initial Draft | Sumit Anand |
|**21-April-2020** | v.1.1 | Installation of specific Version, changing variable directory | Mukesh Tuteja|

Salient Features
----------------
* This role will check if logstash is already installed or not, if not installed, it will install on the remote host the specific version on ubuntu os and default on centos.

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
  * Elasticsearch

Role Variables
--------------
|**Name**| **Default value**| **Description**|
|--|--|--|
|Node.name |Test |Name of the node|
|logstash_version |7 |Major version of logstash to be installed|
|logstash_specific_version |7.3.0 | Uncomment this variable to install specific version of logstash|
|elasticSearchIp |192.168.0.225 | Ip of elasticsearch|
|elasticSearchPort |9200 |Port of elasticsearch|
|logstash_ms_heap_size |512m |Minimum heap size|
|logstash_mx_heap_size |512m |Maximum heap size|
|Queue_page_capacity |250mb |Maximum size of a queue page in bytes|
|Queue_max_bytes |512mb |Total capacity of the queue in number of bytes|
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

Future Proposed Changes
-----------------------
Provide specific version install capability on CentOS.


License
-------

BSD

Author Information
------------------

- Sumit Anand
