asterisk-config-deploy
=========

An Ansible role that deploys Asterisk config files/dialplan from a git repository

The role will checkout configuration files from a git repository into a working
directory and then symlink these files into the asterisk config directory.

WARNING: This will delete your original asterisk config files! Do not run on an existing server.

Requirements
------------

Requires a working asterisk installation and a (private) git repository that contains your config files.

Role Variables
--------------

See defaults/main.yml.

Dependencies
------------

No forced dependencies. Choose your preferred method of installing Asterisk. You may wish to take a look at:

https://galaxy.ansible.com/LukasGibb/asterisk/

Example Playbook
----------------

Obviously you will need to pass in pass in your git repository details (not the example/default ones):

    - hosts: pabxservers
      vars: 
        asterisk-config-deploy-repo-protocol: "https://" 
        asterisk-config-deploy-repo-url: "github.com/myusername/myasteriskconfig"
        asterisk-config-deploy-repo-username: "myusername"
        asterisk-config-deploy-repo-password: "SuperSecretPassword"
      
      roles:
        - LukasGibb.asterisk
        - LukasGibb.asterisk-config-deploy

License
-------

MIT

Author Information
------------------

This role was created in 2018 by [Lukas Gibb](https://github.com/LukasGibb), from [CloudJourneyman.com](http://www.cloudjourneyman.com/)
