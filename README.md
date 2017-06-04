# WLS-Playbook
Ansible で WebLogic Server をインストールします。  

Playbook of ansible.  
This playbook uses to install Oracle WebLogic Server.

## Features

+ Java のインストール
+ WebLogic Server のインストール
+ ドメインの作成
  * 管理サーバと管理対象サーバ 2 台構成


+ Install Java
+ Install WebLogic Server
+ Create WLS Domain
  * AdminServer + ManagedServer x 2

## Requirement

#### Control Machine
+ Python 2.6+
+ Ansible 2.2+

#### Managed Node
+ RHEL,CentOS (6,7)

##### references
+ [Control Machine Requirements](http://docs.ansible.com/ansible/intro_installation.html#control-machine-requirements)
+ [Managed Node Requirements](http://docs.ansible.com/ansible/intro_installation.html#managed-node-requirements)


## Usage

##### Java と WebLogic Server のインストール

```shell
ansible-playbook -i production site.yml --tags="install"
```

##### ドメインの作成

```shell
ansible-playbook -i production site.yml --tags="create"
```
##### WebLogic Server のアンインストール

```shell
ansible-playbook -i production site.yml --tags="uninstall"
```




