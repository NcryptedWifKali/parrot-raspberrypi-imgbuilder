pipeline {
  agent any
  stages {
    stage('setup') {
      steps {
        ws(dir: '/opt/jenkins/parrot-raspberry') {
          sh 'sudo apt-get install live-build qemu-user-static tar gzip xz-utils gdisk unzip wget kpartx lvm2 dosfstools coreutils parted xfsprogs'
        }
        
      }
    }
    stage('configure') {
      steps {
        ws(dir: '/opt/jenkins/parrot-raspberry') {
          sh '''make clean
./configure'''
        }
        
      }
    }
    stage('build') {
      steps {
        ws(dir: '/opt/jenkins/parrot-raspberry') {
          sh 'make -j8'
        }
        
      }
    }
  }
}