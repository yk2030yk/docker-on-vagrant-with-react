```
# 必要なものをインストール
$ brew cask install virtualbox
$ brew cask install vagrant
$ brew install mutagen-io/mutagen/mutagen

# ubuntuのboxを追加する
$ vagrant box add ubuntu/xenial64
$ vagrant box list

# vagrantのプラグインを追加する
$ vagrant plugin install vagrant-disksize vagrant-hostsupdater vagrant-mutagen vagrant-docker-compose

# ssh configがないとvagrant up時にエラーになるので作成しておく
$ touch /Users/t_negishi/.ssh/config

# vagrantを起動する
$ vagrant up
```
