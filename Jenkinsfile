pipeline {
  agent {
    docker {
      image 'ubuntu:16.04'
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
      }
    }
  }
}