## -*- mode: ruby -*-
## vi: set ft=ruby :

## build vagrant instances
Vagrant.configure(2) do |config|
    ## general application
    config.vm.define 'main' do |main|
        ## local variables
        atlas_repo        = 'jeff1evesque'
        atlas_box         = 'trusty64'
        box_version       = '1.2.0'
        box_checksum      = '0bf7b36547e38adf0424735c9c638e17'
        box_checksum_type = 'md5'
        document_version  = '0.7'
        cwd               = '/vagrant'

        ## increase RAM to ensure scrypt doesn't exhaust memory
        main.vm.provision 'shell' do |shell|
            shell.path = 'compile'
            shell.args = [document_version, cwd]
        end

        main.vm.box                        = "#{atlas_repo}/#{atlas_box}"
        main.vm.box_version                = box_version
        main.vm.box_download_checksum      = box_checksum
        main.vm.box_download_checksum_type = box_checksum_type
    end
end