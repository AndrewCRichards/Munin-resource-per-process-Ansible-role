Role Name
=========

Ansible role to generate and install custom Munin memory- and cpu- per-process plugins

Requirements
------------

This Munin plugin should work on most or all Linux systems; it uses 'ps', 'awk' and 'bash'.
It's been developed on Debian and Ubuntu systems so paths may need tweaking on other distros.

Role Variables
--------------

These variables can be set for this role; see defaults/main.yml for their default values:

 - munin_resource_pp_services: The list of processes to be graphed. These are process names as reported by 'ps', also special values 'kernel' (system/kernel entries shown [in square brackets]) and 'other' (aggregate of all non-specified processes)
 - munin_resource_pp_target_dir

Dependencies
------------

None that I can think of. Your target system needs to provide 'ps', 'awk' and 'bash' which are
all pretty ubiquitous so probably already setup on the target system.

Example Playbook
----------------

    - hosts: my_servers
      roles:
         - { role: munin_resource_per_process, munin_resource_pp_services: [ "apache2", "mysqld", "kernel", "other" ] }

License
-------

GPLv2

Copyright (C) 2018  Andrew Richards

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License along
with this program; if not, write to the Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.

Author Information
------------------

Andrew Richards www.acrconsulting.co.uk
