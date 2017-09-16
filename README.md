# SIG.com Ansible Playbooks
This respository contains the various ansible playbooks that SIG.com utilizes
to automate deploying and scaling of the various projects. For more information
on how ansible works, please look [here](https://docs.ansible.com/). This
documentation will assume prior knowledge to ansible and will not attempt to
teach various concepts or terminology that anisble uses.

## Ansible Setup
In order to setup ansible on your machine, simply download any supported python
version from [here](https://www.python.org/downloads/) or your package manager
with pip. For Ubuntu 16.04, the following commands will download python:
```bash
sudo apt install python3 python3-pip
```

Ansible is just a python package so use pip to install the `ansible`
package like so:
```bash
pip3 install ansible
```

## Running Ansible
In order to deploy the entire website onto a single node, run the following
command:
```bash
ansible-playbook -i <inventory file> site.yml --ask-become-pass
```

## Playbooks
### site.yml
Currently, the only playbook which we are utilizing is the `site.yml` playbook.
In this playbook, the entirety of the stack (django, postgreSQL, nginx, uwsgi)
is deployed onto a single node. The acm.mst.edu repository is cloned to
`/var/django/<build_url>/` where `<build_url>` is the url located in the nginx
`server_name` configuration option.
