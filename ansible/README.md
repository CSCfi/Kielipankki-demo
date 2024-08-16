# Setting up Kielipankki's demo server on Pouta

## Prerequisites

- [Access to Pouta](https://docs.csc.fi/accounts/how-to-add-service-access-for-project/)
- Your cPouta project's [OpenStack RC file](https://docs.csc.fi/cloud/pouta/install-client/#configure-your-terminal-environment-for-openstack)
- Key pair for cPouta instances. Created in https://pouta.csc.fi/ (Project > Compute > Key Pairs) and must be named "kielipouta".

## Clone the git repository

Clone this repository and navigate to the correct directory.


## Install requirements
For Python requirements, it is recommended to use a virtual environment:
```
$ virtualenv .venv -p python3
$ source .venv/bin/activate
$ pip install -r requirements_dev.txt
```

The activation step must be done separately for each new session.

## Source your cPouta (OpenStack) auth file.

```
$ source project_2000680-openrc.sh
```

## Install Ansible requirements

$ ansible-galaxy collection install -r requirements.yml


## Run ansible playbook

```
$ ansible-playbook -i inventories/prod.yml demo.yml
```
