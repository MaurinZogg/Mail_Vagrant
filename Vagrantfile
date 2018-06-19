Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest:443, host:4443, auto_correct: true
  config.vm.network "forwarded_port", guest:25, host:2500, auto_correct: true
  config.vm.network "forwarded_port", guest:110, host:1100, auto_correct: true
  config.vm.network "forwarded_port", guest:143, host:1430, auto_correct: true
  config.vm.network "forwarded_port", guest:2000, host:2000, auto_correct: true
  config.vm.synced_folder "/home/vazogg/Vagrant/Mail_Vagrant", "/var/sync/"
  config.vm.hostname = "mail"
  # config.ssh.pty = true
config.vm.provider "virtualbox" do |vb|
  vb.memory = "1024"  
  vb.name = "mail"
end
config.vm.provision "shell", inline: <<-SHELL
	sudo apt-get update
	sudo apt-get upgrade
SHELL
end