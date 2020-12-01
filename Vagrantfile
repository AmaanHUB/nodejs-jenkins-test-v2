# Install required plugins
required_plugins = ["vagrant-hostsupdater"]
required_plugins.each do |plugin|
    exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? plugin
end

Vagrant.configure("2") do |config|

  # Do database first
  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/bionic64"
    db.vm.network "private_network", ip: "192.168.33.20"
    db.hostsupdater.aliases = ["database.local"]
    db.vm.provision "shell", path: "environment/db/provision.sh", privileged: false
  end

  config.vm.define "app" do |app|
    app.vm.box = "ubuntu/bionic64"
    app.vm.network "private_network", ip: "192.168.33.10"
    app.hostsupdater.aliases = ["development.local"]
    app.vm.synced_folder "./app", "/app"
    app.vm.synced_folder "./nginx/", "/home/vagrant/configs/"
    app.vm.provision "shell", path: "environment/app/provision.sh", privileged: false
  end

end
