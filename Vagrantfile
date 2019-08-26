Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest: 80, host: 80, host_ip: "127.0.0.1"
  config.vm.network "forwarded_port", guest: 3306, host: 3306
  config.vm.synced_folder "C:/Users/Elime/PhpstormProjects/rubard-test", "/var/www/rubardtest"
  config.vm.provision "shell", path: "C:/Users/Elime/PhpstormProjects/rubard-test/vagrant/setup.sh"
  config.vm.provider "virtualbox" do |vb|
      vb.customize [ "modifyvm", :id, "--uart1", "0x3F8", "4" ]
      vb.customize [ "modifyvm", :id, "--uartmode1", "file", File.join(Dir.pwd, "/vagrant/vm-console.log") ]
  end
end