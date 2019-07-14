# ansible-lamp-docker
This Ansible playbook is design for Ubuntu 18.04 LTS

## roles

#### BASE - default user is ubuntu
You can override it by
- { role: base, system_user: ubuntu }

#### SWAP - default swapsize is 512MB
You can override it by
- { role: swapfile, swapfile_size: 1GB }

#### SHELL - oh-my-zsh
You can override it by
- { role: shell, shell_user: ubuntu, shell_theme: tjkirch }

#### PHP - Switch within php5 or php7.2
PHP option (choose one):
- { role: php }
- { role: php5 }

#### DOCKER - With some awsome default templates and shellscripts
Docker-compose location : /srv

You can override the default Mariadb password on docker-compose.yml by
- { role: docker, mysql_password: CHANG3M3@2019 }
