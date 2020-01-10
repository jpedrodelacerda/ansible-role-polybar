polybar
=========

A simple role for installation and configuration of polybar.

Requirements
------------

Archlinux
[Ansible AUR](https://github.com/kewlfft/ansible-aur)


Role Variables
--------------

This role will install the given `polybar_version`.

The configuration file and launch created by this role can be specified via `polybar_config_path` and `polybar_launch_path`. They both default to `$HOME/.config/polybar/{config,launch.sh}`

A header and colors can be set on `polybar_header` and `polybar_colors`.
```
polybar_header: My header
polybar_colors:
  base00: '#002b36'
```

Bars are configured via `polybar_bars`.
```
polybar_bars:
  - name: main
    config:
	  width: 100%
	  height: 15
	  ...
```

Modules are configured via `polybar_modules`.
```
polybar_modules:
  - name: bspwm
    config:
	  type: internal/bspwm
      ws-icon-0: "1;"
	  ...
```

For battery and network modules, the role will try to find the respective name for:
- Battery - `polybar_power_supply_battery`
- Adapter - `polybar_power_supply_adapter`
- Wired interface - `polybar_net_interface_eth`
- Wireless interface - `polybar_net_interface_wireless`
> They can be overwritten using the respective variable.

Usage Notes
-----------

Please be sure to escape special characters or use '' (single-quotes) on the string.

Dependencies
------------

None.

Example Playbook
----------------

```
- hosts: localhost
  roles:
     - { role: jpedrodelacerda.polybar }
```

License
-------

MIT
