[![Build Status](https://travis-ci.org/yabhinav/ansible-role-hadoop_repo.svg?branch=master)](https://travis-ci.org/yabhinav/ansible-role-hadoop_repo)

Ansible Role: Hadoop Repo Tasks 
=================================
This role installs repositories required by other roles like :

- AMBARI
- Hortonworks Data Platform - HDP
- HDP-UTILS

These are pre-requisites for other roles that install ambariserver, ambariagent , hdp stack and  applications

Requirements
------------

This role only is needed/runs on RedHat.

Successfully tested on RHEL6.x


Role Variables
------------
```yaml

# Ambari Version
ambari_release_version : '2.2.2.18-1'
ambari_major_version : '2.x' 

# HDP Stack Version
hdp_release_version : '2.4.2.0'
hdp_major_version : '2.x'

# HDP UTILS Version
hdputil_release_version : '1.1.0.21'

# Repositories to be setup on hosts
hadoop_repolist : ['ambari_repo', 'hdp_repo', 'hdputil_repo']

# If Internal Replicated Repository of HWX HDP use that url
repo_base_url: 'http://public-repo-1.hortonworks.com'

```


Dependencies
------------

None.


Example Playbook
----------------

```yaml
- hosts: localhost
  become_user: True
  gather_facts: True
  
  roles:
    - yabhinav.hadoop_repo
```

Issues
------


License
-------

MIT


Author Information
------------------

Created by [Abhinav Yalamanchili](https://yabhinav.github.com)
