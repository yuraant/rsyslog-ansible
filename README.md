# rsyslog-ansible
Installs and configures rsyslog

### Playbook
Default playbook rsyslog.yml installs rsyslog with default settings.

Ansible role accepts parameters:
● logging custom files
● selecting external log server to send logs to

example: 
````
- hosts: all
  vars:
    rsyslog_apps:
      - name: [your_app_name]
        priority: [your_app_priority | example: 42]
        lines:
          - "*.* -/var/log/your_app_name].log"
    rsyslog_udp_enable: true
    rsyslog_udp_address: 127.0.0.1
    rsyslog_udp_port: 514
  roles:
    - rsyslog
````
