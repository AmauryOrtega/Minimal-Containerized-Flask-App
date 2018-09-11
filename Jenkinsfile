pipeline {
  agent any
  stages {
    stage('Build') {
      agent {
        docker {
          image 'hello-world'
        }

      }
      steps {
        sh '''#docker-compose up -d --build
echo "desde hello-world"
uname -a'''
      }
    }
    stage('Status') {
      steps {
        sh '''docker ps -a
docker images -a
docker volume ls
docker network ls'''
      }
    }
    stage('Turndown') {
      steps {
        input 'Terminaste con las pruebas?'
      }
    }
  }
}