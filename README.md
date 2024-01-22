Ansible Role: Scrutiny Spoke
=========

Installs the Collector of the [Scrutiny Project](https://github.com/AnalogJ/scrutiny), a WebUI-based tool for Hard Drive S.M.A.R.T monitoring.

The latest version of the Scrutiny Spoke will be automatically installed to your servers that you specify in your playbook.



Role Variables
--------------

The role uses the following variables with their default values:
```yaml
scrutiny_api_url: "http://localhost:8080"
scrituny_logfile_location: "/var/log/scrutiny.log"
scrutiny_loglevel: "ERROR"   # INFO, DEBUG
```

Usually you want to set the `scrutiny_api_url` to your Scrutiny API/backend. Instructions on how to install that are provided [here](https://github.com/AnalogJ/scrutiny/blob/master/docs/INSTALL_HUB_SPOKE.md).



Other than that, the `inventory_hostname` will be used automatically to set the host label for Scrutiny.



Installation
----------------

Just clone this repository inside the `roles/`-folder of your Ansible project. After that, you can include it in your playbooks as described below.


Example Playbook
----------------

The role can be executed on specific hosts with following playbook:

```yaml
- name: Install Scrutiny Spoke
  hosts: <hosts>
  gather_facts: false

  roles:
  - role: scrutiny-spoke
```

The API URL can be set in the inventory:
```yaml
all:
  vars:
    scrutiny_api_url: "http://<your-server>:<port>"
```
