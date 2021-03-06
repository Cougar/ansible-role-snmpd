## snmpd [![Build Status](https://travis-ci.org/Oefenweb/ansible-snmpd.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-snmpd)

Set up snmp(d) in Debian-like systems.

#### Requirements

None

#### Variables

* `snmpd_install` [default: `[lm-sensors]`]: Additional packages to install
* `snmpd_mibs` [default: `UCD-SNMP-MIB`]: MIBs to load
* `snmpd_run` [default: `true`]: Snmpd control (true means start daemon)
* `snmpd_opts` [default: `'-LS4d -Lf /dev/null -u snmp -g snmp -I -smux -p /var/run/snmpd.pid'`]: Snmpd options (use syslog, close stdin/out/err)
* `snmpd_trapd_run` [default: `false`]: Snmptrapd control (true means start daemon)
* `snmpd_trapd_opts` [default: `'-Lsd -p /var/run/snmptrapd.pid'`]: Snmptrapd options (use syslog)
* `snmpd_snmpd_compat` [default: `false`]: Create symlink on Debian legacy location to official RFC path

* `snmpd_agent_address` [default: `['udp:161', 'udp6:[::1]:161']: Agent address

* `snmpd_internal_user`: [default: see defaults.yml]: Internal user. **Make sure to change!**

* `snmpd_users`: [default: see defaults.yml]: Additional users. **Make sure to change!**
* `snmpd_sys_location` [default: `''`]: System location
* `snmpd_sys_contact` [default: `Root <root@localhost>`]: System contact

* `snmpd_default_monitors` [default: `true`]:
* `snmpd_link_up_down_notifications` [default: `true`]:

## Dependencies

None

#### Example

```yaml
---
- hosts: all
  roles:
  - snmpd
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-snmpd/issues)!
