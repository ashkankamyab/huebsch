# -*- mode: ruby -*-
# vi: set ft=ruby :

ubuntu = {
  "ubnt0" => "192.168.56.11" # You need "," if you enable ubunt1
  # "ubnt1" => "192.168.56.11"
}
rocky9 = {
  "roky0" => "192.168.56.21" # You need "," if you enable roky1
  # "roky1" => "192.168.56.11"
}

fedora = {
  "fdra0" => "192.168.56.31" # You need "," if you enable fdra1
  # "fdra1" => "192.168.56.11"
}

debian = {
  "dbin0" => "192.168.56.41" # You need "," if you enable dbin1
  # "dbin1" => "192.168.56.11"
}

Vagrant.configure("2") do |config|
  ubuntu.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "generic/ubuntu2204"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.memory = 1024
          v.cpus = 1
      end
    end
  end
  config.vm.provision "shell" do |s|
    ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
    s.inline = <<-SHELL
      mkdir -p /root/.ssh
      echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
      echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
      chmod 700 /root/.ssh
    SHELL
  end
end

Vagrant.configure("2") do |config|
  rocky9.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "generic/rocky9"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.memory = 1024
          v.cpus = 1
      end
    end
  end
  config.vm.provision "shell" do |s|
    ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
    s.inline = <<-SHELL
      mkdir -p /root/.ssh
      echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
      echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
      chmod 700 /root/.ssh
    SHELL
  end
end

Vagrant.configure("2") do |config|
  fedora.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "generic/fedora37"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.memory = 1024
          v.cpus = 1
      end
    end
  end
  config.vm.provision "shell" do |s|
    ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
    s.inline = <<-SHELL
      mkdir -p /root/.ssh
      echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
      echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
      chmod 700 /root/.ssh
    SHELL
  end
end

Vagrant.configure("2") do |config|
  debian.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "generic/debian11"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.memory = 1024
          v.cpus = 1
      end
    end
  end
  config.vm.provision "shell" do |s|
    ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
    s.inline = <<-SHELL
      mkdir -p /root/.ssh
      echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
      echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
      chmod 700 /root/.ssh
    SHELL
  end
end