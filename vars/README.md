# Vars Hirerachy 

    {{ ansible_distribution }}-{{ ansible_distribution_version }}
    {{ ansible_distribution }}
    {{ ansible_os_family }}
    defaults

# On CentOS-6.6 this would expand to:

    CentOS-6.6
    CentOS
    RedHat
    defaults

# On Ubuntu 12.04 this would expand to 

   Ubuntu-12.04
   Ubuntu
   Debian
   defaults


 # Usage in task.xml:
 
- name: Gather OS Specific Variables
  include_vars: "{{ item }}"
  with_first_found:
    - "../vars/{{ ansible_distribution }}-{{ ansible_distribution_version }}.yml"
    - "../vars/{{ ansible_distribution }}.yml"
    - "../vars/{{ ansible_os_family }}.yml"
    - "../vars/defaults.yml"
