Vagrant.configure(2) do |config|
  config.vm.box = "bento/centos-7.2"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder ".", "/vagrant/ansible-tomcat", create: true, mount_options: ['dmode=777','fmode=666']
  config.vm.provision "shell", inline: <<-SHELL
    yum install -y epel-release
    yum install -y ansible

    cd /vagrant/ansible-tomcat/tests

    ansible-playbook -i hosts playbook.yml
  SHELL
end
