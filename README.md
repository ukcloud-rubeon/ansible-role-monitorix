Monitorix
=========

Install and configure the Monitorix lightweight system resource monitoring
service.

![Screen Shot](px/screenshot.png)

Requirements
------------

Currently requires no external modules.  Tested only on CentOS (Ubuntu/Debian planned)

Role Variables
--------------

The basic values from Monitorix's config file are represented in vars/main.yaml:

```yaml

monitorix_config_title: System Monitoring (Monitorix)
monitorix_config_hostname: "{{ ansible_ssh_host }}"
monitorix_config_theme_color: black
monitorix_config_refresh_rate: 150
monitorix_config_base_dir: /var/lib/monitorix/www
monitorix_config_base_url: /monitorix
monitorix_config_base_cgi: /monitorix-cgi
monitorix_config_base_lib:  /var/lib/monitorix/
monitorix_config_httpd_builtin_enabled: y
monitorix_config_httpd_builtin_port: 8080
monitorix_config_httpd_builtin_user: nobody
monitorix_config_httpd_builtin_group: nobody
monitorix_config_httpd_builtin_log_file: /var/log/monitorix-httpd

monitorix_config_log_file: /var/log/monitorix
monitorix_config_secure_log: /var/log/secure
monitorix_config_mail_log: /var/log/maillog
monitorix_config_milter_gl: /var/milter-greylist/greylist.db
monitorix_config_imap_log: /var/log/imap
monitorix_config_hylafax_log: /var/spool/hylafax/etc/xferfaxlog
monitorix_config_cups_log: /var/log/cups/page_log
monitorix_config_ftp_log: /var/log/proftpd/access.log
monitorix_config_fail2ban_log: /var/log/fail2ban.log
monitorix_config_spamassassin_log: /var/log/maillog
monitorix_config_clamav_log: /var/log/clamav/clamav.log
monitorix_config_cg_logdir: /var/CommuniGate/SystemLogs/
monitorix_config_squid_log: /var/log/squid/access.log


```
Dependencies
------------

None.

Example Playbook
----------------

```yaml
- name: Setup Monitoring
  hosts: poc-servers
  become: true
  tags:
    - monitoring
  roles:
    - role: monitorix
```
License
-------

BSD

Author Information
------------------
- Eric Williams <ewilliams@ukcloud.com>
