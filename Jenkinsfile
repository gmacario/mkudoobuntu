pipeline {
  agent {
    dockerfile {
      filename 'buildenv/Dockerfile'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        echo 'INFO: Checking whether module binfmt_misc is installed..'
        sh '''#!/bin/bash
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
        sh '''#!/bin/bash

sudo ./mkudoobuntu.sh udoo-neo myflavour

# EOF'''
      }
    }
  }
}
