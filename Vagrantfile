# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.define "testvm" do |testvm| end

#  config.vm.provider "virtualbox" do |v|
#    v.gui = true
#  end


  config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.verbose = "vv"
  end
 
  if Vagrant.has_plugin?("vagrant-cachier")
    # Configure cached packages to be shared between instances of the same base box.
    # More info on http://fgrehm.viewdocs.io/vagrant-cachier/usage
    config.cache.scope = :box
  end
end
