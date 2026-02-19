# frozen_string_literal = true

# Talos ISO (use absolute path)
vagrant_dir  = File.dirname(__FILE__)
project_root = File.expand_path(vagrant_dir)
talos_iso    = ENV.fetch('TALOS_ISO', 'talos-metal-amd64-1.12.4.iso')
ISO_PATH     = File.expand_path(File.join(project_root, talos_iso))

Vagrant.configure('2') do |config|
  config.vm.define 'cp01' do |vm|
    vm.vm.provider :libvirt do |domain|
      domain.cpus = 2
      domain.memory = 2048
      log_cp01 = File.expand_path('.log/cp01.log', __dir__)
      domain.serial type: 'file', source: { path: log_cp01 }
      # domain.serial type: 'file', source: { path: File.expand_path('.log/cp01.log') }
      domain.storage :file, size: '4G', type: 'raw'
      domain.storage :file, device: :cdrom, path: ISO_PATH
      domain.boot 'hd'
      domain.boot 'cdrom'
    end
  end

  config.vm.define 'cp02' do |vm|
    vm.vm.provider :libvirt do |domain|
      domain.cpus = 2
      domain.memory = 2048
      log_cp02 = File.expand_path('.log/cp02.log', __dir__)
      domain.serial type: 'file', source: { path: log_cp02 }
      # domain.serial type: 'file', source: { path: File.expand_path('.log/cp02.log') }
      domain.storage :file, size: '4G', type: 'raw'
      domain.storage :file, device: :cdrom, path: ISO_PATH
      domain.boot 'hd'
      domain.boot 'cdrom'
    end
  end

  config.vm.define 'cp03' do |vm|
    vm.vm.provider :libvirt do |domain|
      domain.cpus = 2
      domain.memory = 2048
      log_cp03 = File.expand_path('.log/cp03.log', __dir__)
      domain.serial type: 'file', source: { path: log_cp03 }
      # domain.serial type: 'file', source: { path: File.expand_path('.log/cp03.log') }
      domain.storage :file, size: '4G', type: 'raw'
      domain.storage :file, device: :cdrom, path: ISO_PATH
      domain.boot 'hd'
      domain.boot 'cdrom'
    end
  end

  config.vm.define 'wk01' do |vm|
    vm.vm.provider :libvirt do |domain|
      domain.cpus = 1
      domain.memory = 1024
      log_wk01 = File.expand_path('.log/wk01.log', __dir__)
      domain.serial type: 'file', source: { path: log_wk01 }
      # domain.serial type: 'file', source: { path: File.expand_path('.log/wk01.log') }
      domain.storage :file, size: '4G', type: 'raw'
      domain.storage :file, device: :cdrom, path: ISO_PATH
      domain.boot 'hd'
      domain.boot 'cdrom'
    end
  end
end
