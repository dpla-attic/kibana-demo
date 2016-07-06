Vagrant.configure(2) do |config|
  config.vm.define 'logtest' do |krikri|
    krikri.vm.box = 'ubuntu/trusty64'
    krikri.vm.hostname = 'logtest'
    krikri.vm.network :private_network, ip: '192.168.50.20'
    krikri.vm.network "forwarded_port", guest: 9200, host: 9200
    krikri.vm.network "forwarded_port", guest: 5601, host: 5601
    krikri.vm.provider 'virtualbox' do |vb|
      vb.memory = 1024
    end
    krikri.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'provisioning/provision.yml'
    end
  end
end

