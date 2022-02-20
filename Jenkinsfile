pipeline {
  agent any
  stages {
    stage('clone code') {
      steps {
        sh '''host=\'192.168.55.150,\'
DOCKER_ID=8b3c682f28d9
docker cp ${WORKSPACE}/html 8b3c682f28d9:/mnt
docker exec  $DOCKER_ID  /bin/sh -c "ansible  all -i $host --key-file /mnt/id_rsa -m copy -a \'src=/mnt/html  dest=/usr/share/nginx/\' "'''
      }
    }

  }
}