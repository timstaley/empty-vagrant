#Empty Vagrant

A mostly-empty [Vagrant](https://docs.vagrantup.com) setup. 
Useful for whipping up a quick test-box.

Switches on [vagrant-cachier](http://fgrehm.viewdocs.io/vagrant-cachier), 
to avoid redownloading apt-packages repeatedly, if you run

    vagrant plugin install vagrant-cachier
    
first. 

Also drops in an [Ansible](http://docs.ansible.com/) config, so you 
can test Ansible commands directly, instead of needing to re-run 
``vagrant provision`` each time. (Note you'll need to edit the path to the 
ssh key under 'ssh_args' if you change the virtual machine name from 'testvm'.)
