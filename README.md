# Nutanix Role to register a Nutanix cluster to a Prism Central instance

This Ansible role will register a Nutanix cluster to a Prism Central instance. This role should will only run against a Nutanix cluster


## Role Variables

Inputs

| Variable                        | Required | Default | Choices                   | Comments                                                                             |
|---------------------------------|----------|---------|---------------------------|--------------------------------------------------------------------------------------|
| nutanix_host                    | yes      |         |                           | The IP address or FQDN for the Prism (Element only) to which you want to connect.    |
| nutanix_username                | yes      |         |                           | A valid username with appropriate rights to access the Nutanix API.                  |
| nutanix_password                | yes      |         |                           | A valid password for the supplied username.                                          |
| nutanix_port                    | no       | 9440    |                           | The Prism TCP port.                                                                  |
| validate_certs                  | no       | no      | yes | no                  | Whether to check if Prism UI certificates are valid.                                 |
| nutanix_pc_register_pc_ip       | yes      |         |                           | The IP address of the Prism Central to register with.                                |
| nutanix_pc_register_pc_username | no       | "admin" |                           | The username to authenticate with Prism Central.                                     |
| nutanix_pc_register_pc_password | yes      |         |                           | The password to authenticate with Prism Central.                                     |


## Dependencies

NA

## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
    - grdavies.role_nutanix_pe_register_pc
  vars:
    nutanix_host: 10.38.185.37
    nutanix_username: admin
    nutanix_password: nx2Tech165!
    nutanix_pc_register_pc_ip: 10.38.185.39
    nutanix_pc_register_pc_username: admin
    nutanix_pc_register_pc_password: nx2Tech165!
```

## License

See LICENSE.md

## Author Information

Ross Davies
