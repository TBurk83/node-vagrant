Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.synced_folder ".", "/var/www/react-webpack"
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -
    su vagrant
    apt-get install -y nodejs
    mkdir /home/vagrant/node_modules
    cd /var/www/react-webpack
    ln -s /home/vagrant/node_modules/ node_modules
    npm install -g -y gulp
  SHELL
end