[![Build Status](https://travis-ci.org/while-true-do/ansible-role-wakeonlan.svg?branch=master)](https://travis-ci.org/while-true-do/ansible-role-wakeonlan)

# Ansible Role: wakeonlan
| This role can be used to power on a host via magic packet with wake on LAN.

## Motivation

Some hosts are not up all the time, due to energy saving considerations.
To apply various tasks to the powered off host it needs to be powered on and this is
exactly where this role is needed.

## Installation

Install from [Ansible Galaxy](https://galaxy.ansible.com/while_true_do/wakeonlan)

```
ansible-galaxy install while_true_do.wakeonlan
```

Install from [Github](https://github.com/while-true-do/ansible-role-wakeonlan)

```
git clone https://github.com/while-true-do/ansible-role-wakeonlan.git while_true_do.wakeonlan
```

## Requirements

Used Modules:

-   [command_module](https://docs.ansible.com/ansible/latest/modules/command_module.html)
-   [set_fact_module](https://docs.ansible.com/ansible/latest/modules/set_fact_module.html)
-   [setup_module](https://docs.ansible.com/ansible/latest/modules/setup_module.html)
-   [wait_for_connection_module](https://docs.ansible.com/ansible/latest/modules/wait_for_connection_module.html)
-   [wakeonlan_module](https://docs.ansible.com/ansible/latest/modules/wakeonlan_module.html)

## Dependencies

None.

## Role Variables

```yaml
# defaults/main.yml for wakeonlan

# wtd_wakeonlan_mac: ""
wtd_wakeonlan_broadcast: "255.255.255.0"
wtd_wakeonlan_delegation_host: "localhost"
wtd_wakeonlan_port: "7"

wtd_wakeonlan_wait_for_connection_timeout: "600"
```

## Example Playbook

Simple Example:

```yaml
- hosts: servers
  gather_facts: no
  roles:
    - { role: while_true_do.wakeonlan }
```

Advanced Example:

```yaml
- hosts: servers
  gather_facts: no
  roles:
    - { role: while_true_do.wakeonlan,
        wtd_wakeonlan_mac: "aa:bb:cc:dd:ee:ff",
        wtd_wakeonlan_delegation_host: "home-router"
      }
```

## Testing

All tests are located in [test directory](./tests/).

Basic testing:

```
bash ./tests/test-ansible.sh
bash ./tests/test-spelling.sh
bash ./tests/test-whitespace.sh
```

## Contribute / Bugs

Thank you so much for considering to contribute. Every contribution helps us.
We are really happy, when somebody is joining the hard work. Please have a look
at the links first.

-   [Code of Conduct](./docs/CODE_OF_CONDUCT.md)
-   [Contribution Guidelines](./docs/CONTRIBUTING.md)
-   [Create an issue or Request](https://github.com/while-true-do/ansible-role-wakeonlan/issues)
-   [See who was contributing already](https://github.com/while-true-do/ansible-role-wakeonlan/graphs/contributors)

## License

This work is licensed under a [BSD License](https://opensource.org/licenses/BSD-3-Clause).

## Author Information

Site: [while-true-do.org](https://while-true-do.org)

Mail: [hello@while-true-do.org](mailto:hello@while-true-do.org)
