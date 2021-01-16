![](https://img.shields.io/badge/Ansible-orchestrator-green.svg?logo=angular&style=for-the-badge)

>__Please note that the original design goal of this role was more concerned with the initial installation and bootstrapping environment, which currently does not involve performing continuous maintenance, and therefore are only suitable for testing and development purposes,  should not be used in production environments. The author does not guarantee the accuracy, completeness, reliability, and availability of the role content. Under no circumstances will the author be held responsible or liable in any way for any claims, damages, losses, expenses, costs or liabilities whatsoever, including, without limitation, any direct or indirect damages for loss of profits, business interruption or loss of information.__

>__请注意，此角色的最初设计目标更关注初始安装和引导环境，目前不涉及执行连续维护，因此仅适用于测试和开发目的，不应在生产环境中使用。作者不对角色内容之准确性、完整性、可靠性、可用性做保证。在任何情况下，作者均不对任何索赔，损害，损失，费用，成本或负债承担任何责任，包括但不限于因利润损失，业务中断或信息丢失而造成的任何直接或间接损害。__
___

<p><img src="https://raw.githubusercontent.com/goldstrike77/goldstrike77.github.io/master/img/logo/logo_orchestrator.png" align="right" /></p>

__Table of Contents__

- [Overview](#overview)
- [Requirements](#requirements)
  * [Operating systems](#operating-systems)
  * [Versions](#Versions)
- [ Role variables](#Role-variables)
  * [Main Configuration](#Main-parameters)
  * [Other Configuration](#Other-parameters)
- [Dependencies](#dependencies)
- [Example Playbook](#example-playbook)
  * [Hosts inventory file](#Hosts-inventory-file)
  * [Vars in role configuration](#vars-in-role-configuration)
  * [Combination of group vars and playbook](#combination-of-group-vars-and-playbook)
- [License](#license)
- [Author Information](#author-information)
- [Contributors](#Contributors)

## Overview
Orchestrator is a MySQL high availability and replication management tool, runs as a service and provides command-line access, HTTP API and Web interface. 

## Requirements
### Operating systems
This Ansible role installs orchestrator on Linux operating system, including establishing a filesystem structure and server configuration with some common operational features. Will works on the following operating systems:

  * CentOS 7

### orchestrator versions

The following list of supported the orchestrator releases:

* 3+

## Role variables
### Main parameters #
There are some variables in defaults/main.yml which can (Or needs to) be overridden:

##### General parameters
* `orchestrator_is_install`: A boolean value, whether install the Orchestrator.
* `orchestrator_cluster_name`: Cluster name of servers that runs as a highly available service.
* `orchestrator_path`: Specify the Orchestrator data directory.
* `orchestrator_ui_user`: Management console authentication user.
* `orchestrator_ui_pass`: Management console authentication password.
* `orchestrator_ui_ssl`: A boolean value, whether Encrypting client communications.

##### Listen port
* `orchestrator_port_ui`: Orchestrator Web UI listen port.
* `orchestrator_port_agent`: Orchestrator Agent listen port.
* `orchestrator_port_raft`: Orchestrator Raft listen port.

##### MySQL parameters
* `orchestrator_mysql_user`: MySQL topology control account name.
* `orchestrator_mysql_pass`: MySQL topology control account password.
* `orchestrator_mysql_port`: MySQL topology control instance listen port.


### Other parameters
There are some variables in vars/main.yml:

## Dependencies
- Ansible versions >= 2.8
- Python >= 2.7.5

## Example

### Hosts inventory file
See tests/inventory for an example.

### Vars in role configuration
Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: all
  roles:
     - role: ansible-role-linux-orchestrator
```

### Combination of group vars and playbook
You can also use the group_vars or the host_vars files for setting the variables needed for this role. File you should change: group_vars/all or host_vars/`group_name`.

```yaml
orchestrator_is_install: false
orchestrator_cluster_name: 'cluster01'
orchestrator_path: '/data'
orchestrator_ui_user: 'admin'
orchestrator_ui_pass: 'changeme'
orchestrator_ui_ssl: false
orchestrator_port_ui: '3002'
orchestrator_port_agent: '3003'
orchestrator_port_raft: '10008'
orchestrator_mysql_user: 'orchestrator'
orchestrator_mysql_pass: 'changeme'
orchestrator_mysql_port: '3306'
```

## License
![](https://img.shields.io/badge/MIT-purple.svg?style=for-the-badge)

## Author Information
Please send your suggestions to make this role better.

## Contributors
Special thanks to the [Connext Information Technology](http://www.connext.com.cn) for their contributions to this role.
