Vagrant.configure('2') do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = 'docker-on-vagrant'
  config.vm.network "forwarded_port", host: 3001, guest: 3000

  config.vm.provider :virtualbox do |vb|
    vb.gui = false
    vb.cpus = 2
    vb.memory = 4096
    vb.customize ['modifyvm', :id, '--natdnsproxy1', 'off']
    vb.customize ['modifyvm', :id, '--natdnshostresolver1', 'off']
    vb.customize ['modifyvm', :id, '--audio', 'none']
  end

  config.disksize.size = '30GB'
  config.mutagen.orchestrate = true

  config.vm.synced_folder './', '/home/vagrant/app', type: "rsync",
    rsync_auto: true,
    rsync__exclude: ['.git/', 'node_modules/', 'log/', 'tmp/']

  config.vm.provision :docker, run: 'always'
  config.vm.provision :docker_compose
end