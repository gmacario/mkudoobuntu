pipeline {
  agent {
    dockerfile {
      filename 'buildenv/Dockerfile'
    }
    
  }
  stages {
    stage('Build') {
      steps {
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
