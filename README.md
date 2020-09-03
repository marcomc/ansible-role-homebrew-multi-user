# Homebrew Multi User ansible role
Ansible role to configure Homebrew to be managed by multiple users members of the same group.

It is possible to choose to apply the permissions via ACL or POSIX or both.

## (Soft) Requirements & Dependencies
* [Jeff Geerling](https://github.com/geerlingguy)'s' [geerlingguy.homebrew](https://github.com/geerlingguy/ansible-role-homebrew) which is defined as Ansible Galaxy dependency

### Ansible
It was tested on the following versions:
 * 2.9

### Operating systems
Target MacOS 10.15 possibly earlier versions too (not yet tested)

## Example Playbook
Just include this role in your list.
For example

    - host: all
      vars:
        homebrew_group: "staff"
        hombrew_acl_posix_permissions: yes
      roles:
        - marcomc.homebrew-multi-user

## Variables

    homebrew_user: ""                  # "{{ ansible_user_id }}" # only used for posix permissions
    homebrew_group: "staff"            # the name of the group you want to share the homebrew management
    hombrew_acl_posix_permissions: yes
    hombrew_fix_posix_permissions: no
    homebrew_folders_base:
      - Cellar
      - Homebrew
      - Frameworks
      - Caskroom
      - bin
      - etc
      - include
      - lib
      - opt
      - sbin
      - share
      - share/zsh
      - share/zsh/site-functions
      - var
    homebrew_folders_additional: []


## Continuous integration
This role has (not yet) a travis basic test (for github) only.

## Troubleshooting & Known issues

## Copyright
Marco Massari Calderone (c) 2020

## License
MIT
