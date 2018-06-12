Role Name
=========

Ansible role to generate and install custom Munin memory-per-process plugin

Requirements
------------

This Munin plugin should work on most or all Linux systems; it uses 'ps', 'awk' and 'bash'.
It's been developed on Debian and Ubuntu systems so paths may need tweaking on other distros.

Role Variables
--------------

These variables can be set for this role; see defaults/main.yml for their default values:

 - ar_munin_memory_pp_plugin_services: The list of processes to be graphed. These are process names as reported by 'ps', also special values 'kernel' (system/kernel entries shown [in square brackets]) and 'other' (aggregate of all non-specified processes)
 - ar_munin_memory_pp_plugin_target_dir
 - ar_munin_memory_pp_plugin_name

Dependencies
------------

None that I can think of. Your target system needs to provide 'ps', 'awk' and 'bash' which are
all pretty ubiquitous so probably already setup on the target system.

Example Playbook
----------------

    - hosts: my_servers
      roles:
         - { role: ar_munin_memory_per_process_plugin, ar_munin_memory_pp_plugin_services: [ "apache2", "mysqld", "kernel", "other" ] }

License
-------

GPLv2

Author Information
------------------

Andrew Richards www.acrconsulting.co.uk
