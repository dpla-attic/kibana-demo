Vagrant.configure(2) do |config|
  config.vm.define 'logtest' do |logtest|
    logtest.vm.box = 'ubuntu/xenial64'
    logtest.vm.hostname = 'logtest'
    logtest.vm.network :private_network, ip: '192.168.50.20'
    logtest.vm.network "forwarded_port", guest: 9200, host: 9200
    logtest.vm.network "forwarded_port", guest: 5601, host: 5601
    logtest.vm.provider 'virtualbox' do |vb|
      vb.memory = 2048
    end
    logtest.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'provisioning/provision.yml'
    end
  end
end

