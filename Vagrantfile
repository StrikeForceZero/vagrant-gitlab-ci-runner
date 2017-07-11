# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|  
  config.env.enable
  config.vm.box = "hashicorp/precise64"  
  config.disksize.size = "102400MB" # Bug with vagrant-disksize plugin?

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.extra_vars = {
      "url" => ENV["url"],
      "token" => ENV["token"],
      "name" => ENV["name"],
      "tags" => ENV["tags"],
    }
  end
end

