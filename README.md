## ansiblePhpPlaybook

### Overview

-

easy setup nginx/php/mysql/redis application


### Installation

Please perform the following steps to run

install [vitrualbox](https://www.virtualbox.org/)

```
brew install vagrant
brew install ansible
```

### usage

all setup

```
vagrant up
```

ansible-playbook only run

```
ansible-playbook -i hosts provision_vagrant.yml
```
