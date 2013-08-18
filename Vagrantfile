Vagrant::Config.run do |config|
  config.vm.define :node1 do |node1_config|
    node1_config.vm.box = "node1"
    node1_config.vm.box = "precise32"
    node1_config.vm.network :bridged, :bridge => "wlan0"
    node1_config.vm.provision :chef_client do |chef|
       chef.chef_server_url = "https://api.opscode.com/organizations/opaque"
       chef.validation_key_path = "~/chef-repo/.chef/opaque-validator.pem"
       chef.validation_client_name = "opaque-validator"
       chef.node_name = "node1"
       chef.add_role("base")
       chef.add_role("web")
       end
    end

  config.vm.define :node2 do |node2_config|
    node2_config.vm.box = "node2"
    node2_config.vm.box = "precise32"
    node2_config.vm.network :bridged, :bridge => "wlan0"
    node2_config.vm.provision :chef_client do |chef|
       chef.chef_server_url = "https://api.opscode.com/organizations/opaque"
       chef.validation_key_path = "~/chef-repo/.chef/opaque-validator.pem"
       chef.validation_client_name = "opaque-validator"
       chef.node_name = "node2"
       chef.add_role("base")
       chef.add_role("proxy")       
       end
    end

config.vm.define :node3 do |node3_config|
    node3_config.vm.box = "node3"
    node3_config.vm.box = "precise32"
    node3_config.vm.network :bridged, :bridge => "wlan0"
    node3_config.vm.provision :chef_client do |chef|
       chef.chef_server_url = "https://api.opscode.com/organizations/opaque"
       chef.validation_key_path = "~/chef-repo/.chef/opaque-validator.pem"
       chef.validation_client_name = "opaque-validator"
       chef.node_name = "node3"
       chef.add_role("base")
       chef.add_role("monitoring")
       end
    end
end
