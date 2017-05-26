pipeline {
  agent {
    dockerfile {
      filename 'buildenv/Dockerfile'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        sh '''#!/bin/bash

echo "INFO: Checking whether module binfmt_misc is installed.."

grep -w binfmt_misc /proc/modules >/dev/null || {
    echo "Please execute on your Docker Host: \"sudo modprobe binfmt_misc\""
    exit 1
}
'''
        echo 'INFO: Building'
        sh '''#!/bin/bash

# DEBUG
id
pwd
df -h .
ls -la

# EOF'''

        // To debootstrap a new unnamed image, use:
        //     sudo ./mkudoobuntu.sh <board> <flavour>
        //
        // Branded-release images can be generated with:
        //    sudo RELEASE="2.0 Beta6" ./mkudoobuntu.sh <board> <flavour>
        //
        // To edit a previously debootstrapped rootfs, use:
        //    sudo ./mkudoobuntu.sh <board> <operation>
        //
        // <board> can be: udoo-qdl, udoo-neo.
        //
        // <operation> can be:
        //    install       Install a deb in rootfs from repos
        //    remove        Remove a deb from rootfs
        //    list          List installed pkg in rootfs
        //    reimage       Make a new image from a modified rootfs
        //    shell         Open an interactive shell in a rootfs
        //
        // Valid flavours for udoo-neo are: minimal desktop wyliodrin.

        sh '''#!/bin/bash
    
sudo ./mkudoobuntu.sh udoo-neo desktop

# EOF'''
      }
    }
  }
}
