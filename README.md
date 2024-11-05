# manage_rhel_packages

An Ansible role to manage packages on RHEL systems by installing necessary packages and removing unnecessary ones. The execution of each package category is controlled by boolean variables.

## Requirements

- Ansible 2.9 or higher
- RHEL 8 or 9

## Role Variables

### Control Variables (`defaults/main.yml`)

- `install_basic_packages` (default: `true`): Install basic packages if `true`.
- `install_performance_packages` (default: `false`): Install performance packages if `true`.
- `install_troubleshooting_packages` (default: `false`): Install troubleshooting packages if `true`.
- `remove_unnecessary_packages` (default: `false`): Remove unnecessary packages if `true`.

### Package Lists (`defaults/main.yml`)

- `basic_packages_list`: List of basic packages to install.
- `performance_packages_list`: List of performance packages to install.
- `troubleshooting_packages_list`: List of troubleshooting packages to install.
- `packages_to_remove_list`: List of packages to remove.

## Dependencies

None.

## Example Playbook

```yaml
- name: Manage packages on RHEL servers
  hosts: rhel_servers
  become: yes
  vars:
    install_basic_packages: true
    install_performance_packages: true
    install_troubleshooting_packages: false
    remove_unnecessary_packages: true
  roles:
    - manage_rhel_packages
```

## License

MIT


## Author Information

Allan Roque aroque@redhat.com
