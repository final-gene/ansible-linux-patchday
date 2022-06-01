# Ansible Role `linux_patchday`

## Description

This role allows patching and updating linux systems.

## Installation

```shell
ansible-galaxy install finalgene.linux_patchday
```

## Requirements

None

## Role Variables

| Variable                      | Type     | Default   | Comments                                                                                                                |
|-------------------------------|----------|-----------|-------------------------------------------------------------------------------------------------------------------------|
| linux_patchday_distro_upgrade | boolean  | `false`   | `true` if distribution update should be performed                                                                       |
| linux_patchday_distro_release | string   |           | Name of the target release for distribution update.<br/><br/>e.g. `buster`                                              |
| reboot_timeout                | integer  | `300`     | Maximum seconds to wait for machine to reboot and respond to a test command.                                            |
| pre_reboot_delay              | integer  | `0`       | Seconds to wait before reboot. Passed as a parameter to the reboot command.                                             |
| post_reboot_delay             | integer  | `30`      | Seconds to wait after the reboot command was successful before attempting to validate the system rebooted successfully. |
| reboot_test_command           | string   | `uptime`  | Command to run on the rebooted host and expect success from to determine the machine is ready for further tasks.        |

## Dependencies

None

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: finalgene.linux_patchday
```

## Author

- [Frank Giesecke](https://github.com/frankgiesecke)

## License

This project is under the MIT License. See the [LICENSE](./LICENSE) file for the full license text.

## Copyright

(c) 2022, [final gene](https://github.com/final-gene)
