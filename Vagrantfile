# frozen_string_literal = true

# Talos ISO (use absolute path)
vagrant_dir  = File.dirname(__FILE__)
LOG_DIR      = 'log'
project_root = File.expand_path(vagrant_dir)
talos_iso    = ENV.fetch('TALOS_ISO', 'metal-amd64.iso')
ISO_PATH     = File.expand_path(File.join(project_root, talos_iso))

# Make sure log directory exists on host.
# Use `__dir__` so it’s anchored to the Vagrantfile, not the shell’s CWD
require 'fileutils'
FileUtils.mkdir_p(File.expand_path(LOG_DIR, __dir__))

Vagrant.configure('2') do |config|
  config.vm.define 'cp01' do |vm|
    vm.vm.provider :libvirt do |domain|
      domain.cpus = 2
      domain.memory = 2048

      log_cp01 = File.expand_path("#{LOG_DIR}/cp01.log", __dir__)
      domain.serial type: 'pty'
      domain.serial type: 'file', source: { path: log_cp01 }

      domain.storage :file, size: '8G', type: 'raw'
      domain.storage :file, device: :cdrom, path: ISO_PATH

      domain.boot 'hd'
      domain.boot 'cdrom'
    end
  end

  config.vm.define 'cp02' do |vm|
    vm.vm.provider :libvirt do |domain|
      domain.cpus = 2
      domain.memory = 2048

      log_cp02 = File.expand_path("#{LOG_DIR}/cp02.log", __dir__)
      domain.serial type: 'pty'
      domain.serial type: 'file', source: { path: log_cp02 }

      domain.storage :file, size: '8G', type: 'raw'
      domain.storage :file, device: :cdrom, path: ISO_PATH

      domain.boot 'hd'
      domain.boot 'cdrom'
    end
  end

  config.vm.define 'cp03' do |vm|
    vm.vm.provider :libvirt do |domain|
      domain.cpus = 2
      domain.memory = 2048

      log_cp03 = File.expand_path("#{LOG_DIR}/cp03.log", __dir__)
      domain.serial type: 'pty'
      domain.serial type: 'file', source: { path: log_cp03 }

      domain.storage :file, size: '8G', type: 'raw'
      domain.storage :file, device: :cdrom, path: ISO_PATH

      domain.boot 'hd'
      domain.boot 'cdrom'
    end
  end

  config.vm.define 'wk01' do |vm|
    vm.vm.provider :libvirt do |domain|
      domain.cpus = 1
      domain.memory = 1024

      log_wk01 = File.expand_path("#{LOG_DIR}/wk01.log", __dir__)
      domain.serial type: 'pty'
      domain.serial type: 'file', source: { path: log_wk01 }

      domain.storage :file, size: '8G', type: 'raw'
      domain.storage :file, device: :cdrom, path: ISO_PATH

      domain.boot 'hd'
      domain.boot 'cdrom'
    end
  end
end
