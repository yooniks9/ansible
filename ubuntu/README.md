# ansible-lamp-docker
This Ansible playbook is design for Ubuntu 18.04 LTS

## vars

- system_user: 'ubuntu'
- ansible_distribution_release: (xenial or bionic)
- swapfile_size: 1GB 
- php_mod: (apache2 or fpm)
- mysql_password: "MYSQLPASSWORD"
- domain: YOURDOMAINNAME.com
- subdomain: ( www.YOURDOMAINNAME.com or False )
- ssl: ( True or False )
- email: support@YOURDOMAINNAME.com

## roles

#### BASE - default user is ubuntu
You can override it by
- { role: base, system_user: ubuntu }

#### SWAP - default swapsize is 512MB
You can override it by
- { role: swapfile, swapfile_size: 1GB }

#### SHELL - oh-my-zsh
You can override it by
- { role: shell, system_user: ubuntu, shell_theme: tjkirch }

#### PHP - Switch within php5 or php7.2
PHP option (choose one):
- { role: php }
- { role: php5 }

#### DOCKER - With some awsome default templates and shellscripts
Docker-compose location : /srv

You can override the default Mariadb password on docker-compose.yml by
- { role: docker, mysql_password: CHANG3M3@2019 }

## ansible-playbook cli

#### install sshpass for mac
```
brew install https://raw.githubusercontent.com/kadwanev/bigboybrew/master/Library/Formula/sshpass.rb
```

#### prompt for password
```
ansible-playbook playbook.yml --user=username --ask-sudo-pass
```

#### include password on cli
```
ansible-playbook playbook.yml --user=username --extra-vars "ansible_sudo_pass=yourPassword"
```