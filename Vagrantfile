Vagrant.configure("2") do |config|
  config.vm.box = "HHVM_Ubuntu12"
  config.vm.box_url = "https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box"
  config.vm.synced_folder "./", "/var/www", id: "vagrant-root"

  config.vm.provider :aws do |aws, override|
    aws.access_key_id=''
    aws.secret_access_key=''
    aws.keypair_name = ""
    override.ssh.private_key_path = ""
    aws.instance_type = "t1.micro"
    aws.security_groups = 'HHVM'
    aws.ami = "ami-3d128f07"
    override.ssh.username = "ubuntu"
    aws.region = "ap-southeast-2"
    aws.tags = {
      'Name' => 'HHVM Ubuntu',
     }
  end

  # Enable provisioning with Ansible
  config.vm.provision "ansible" do |ansible|
     ansible.playbook = "ansible/site.yml"
  end
end
