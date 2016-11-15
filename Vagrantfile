# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.define "emptyvm" do |emptyvm| end


  config.vm.provider "virtualbox" do |v|
#    v.gui = true
      v.memory = 512
      v.cpus = 2
  end

  config.vm.provision "shell",
    inline: "sudo apt-get install -y python-minimal"

  config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.verbose = "vv"
      ansible.groups = {
        "vagrantvm" => ["emptyvm"],
      }
  end
 
  if Vagrant.has_plugin?("vagrant-cachier")
    # Configure cached packages to be shared between instances of the same base box.
    # More info on http://fgrehm.viewdocs.io/vagrant-cachier/usage
    config.cache.scope = :box
  end
end
