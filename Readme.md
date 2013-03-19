# Readme

## Description

*ansible-veewee* is an [Ansible](http://ansible.cc) playbook.
The playbook contains tasks to build a Vagrant basebox.

## Requirements

### Ansible

Everything you should know about Ansible is documented on the [Ansible](http://ansible.cc/docs/gettingstarted.html) site...

### Supported platforms

#### Ansible >= 1.0

Any Ansible version >= 1.0 should work. If not, please use the issue tracker to report any bugs.

## Usage

### Get the code

```bash
$ git clone git@github.com:ICTO/ansible-veewee.git
```

### Run the playbook

The playbook is designed to run locally on your machine. The playbook will try to execute sudo to the root user. The *-K* option ensures to ask the sudo password on the command line.

The playbook will prompt for the Veewee template name, the name of your new basebox, and a working directory.

After the playbook run, a .box will appear in the working directory (the one you've provided at the input prompt), which can be used in Vagrant.

```bash
$ ansible-playbook -K veewee.yml
```

### Example output

```
sudo password: 
Choose your template: Debian-7.0-rc1-amd64-netboot
Name your basebox: debianbox
Choose your working directory: /home/tberton/BaseBoxes

PLAY [Basebox builder] ********************* 

GATHERING FACTS ********************* 
ok: [127.0.0.1]

TASK: [Install Vagrant from gems] ********************* 
ok: [127.0.0.1]

TASK: [Install Veewee from gems] ********************* 
ok: [127.0.0.1]

TASK: [Install Veewee-templates-updater from gems] ********************* 
ok: [127.0.0.1]

TASK: [Update Veewee templates] ********************* 
changed: [127.0.0.1]

TASK: [Define a new basebox] ********************* 
changed: [127.0.0.1]

TASK: [Build a new basebox] ********************* 
changed: [127.0.0.1]

TASK: [Export the new basebox] ********************* 
changed: [127.0.0.1]

PLAY RECAP ********************* 
127.0.0.1                      : ok=8    changed=4    unreachable=0    failed=0    
```

## Docs and contact

Veewee: https://github.com/jedi4ever/veewee/blob/master/doc/vagrant.md

Veewee templates updater: https://github.com/mpapis/veewee-templates-updater

Vagrant: http://docs.vagrantup.com/v2/


Read more on the Wiki pages about how this playbook works.

http://icto.ugent.be
