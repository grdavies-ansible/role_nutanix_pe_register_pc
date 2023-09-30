# Nutanix Role to register a Nutanix cluster to a Prism Central instance

This Ansible role will register a Nutanix cluster to a Prism Central instance. This role should will only run against a Nutanix cluster


## Role Variables

Inputs

| Variable                                            | Required | Default | Choices                   | Comments                                                                             |
|-----------------------------------------------------|----------|---------|---------------------------|--------------------------------------------------------------------------------------|
| role_nutanix_pe_register_pc_host                    | yes      |         |                           | The IP address or FQDN for the Prism (Element only) to which you want to connect.    |
| role_nutanix_pe_register_pc_host_username           | yes      |         |                           | A valid username with appropriate rights to access the Nutanix API.                  |
| role_nutanix_pe_register_pc_host_password           | yes      |         |                           | A valid password for the supplied username.                                          |
| role_nutanix_pe_register_pc_host_port               | no       | 9440    |                           | The Prism TCP port.                                                                  |
| role_nutanix_pe_register_pc_host_validate_certs     | no       | false   | true / false              | Whether to check if Prism UI certificates are valid.                                 |
| role_nutanix_pe_register_pc_ip                      | yes      |         |                           | The IP address of the Prism Central to register with.                                |
| role_nutanix_pe_register_pc_username                | no       | "admin" |                           | The username to authenticate with Prism Central.                                     |
| role_nutanix_pe_register_pc_password                | yes      |         |                           | The password to authenticate with Prism Central.                                     |


## Dependencies

- grdavies.role_nutanix_prism_api
- grdavies.role_nutanix_prism_monitor_task

## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
    - grdavies.role_nutanix_pe_register_pc
  vars:
    role_nutanix_pe_register_pc_host: 10.38.185.37
    role_nutanix_pe_register_pc_host_username: admin
    role_nutanix_pe_register_pc_host_password: nx2Tech165!
    role_nutanix_pe_register_pc_ip: 10.38.185.39
    role_nutanix_pe_register_pc_username: admin
    role_nutanix_pe_register_pc_password: nx2Tech165!
```

## License

See LICENSE.md

## Author Information

Ross Davies
