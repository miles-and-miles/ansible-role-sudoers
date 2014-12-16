sudoers
=======

Managing sudoers-files in /etc/sudoers.d/ or any other configured directory.
It might be possible to add groups as user ;) not tested

Requirements
------------

None

Role Variables
--------------

`sudoers_dir_path`: Path to the sudoers-files (/etc/sudoers.d/)
`sudoers_{host,group,all}`: Array of sudoers-definitions

    sudoers_{host,group,all}:
    - cmd_name: Name of the command (required)
      cmd_list: Array of commands (required)
      cmd_users: Array of users (required)

Dependencies
------------

None

Example Playbook
----------------

`some_group_var.yml`:

    sudoers_group:
      - cmd_name: VPN
        cmd_list:
        - "/usr/sbin/openvpn"
        cmd_users:
        - "foo"

`some_playbook.yml`:

    - hosts: vpn_clients
      sudo: yes
      roles:
      - sudoers

License
-------

The MIT License (MIT)

Copyright (c) 2014 Julian Stiller

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Contributing
------------

I welcome contributed improvements and bug fixes via the usual github
workflow:

1. Fork this repository
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new pull request
