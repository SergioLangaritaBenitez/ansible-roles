# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
nodes=3 

(1..nodes).each do |i|
  Vagrant.configure(2) do |config|
    config.vm.box = "bento/ubuntu-22.04"
    config.vm.define "machine-#{i}"
    config.vm.network "private_network", ip: "192.168.56.#{i+1}"
    
    config.vm.provision  "shell" do |s|
      #echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
      #service ssh restart
      #passwd root <<<$'root\nroot\n'

      ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
      s.inline = <<-SHELL
        echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
        echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
      SHELL
    #   #apt-get install -y apache2
    end
  end
end
