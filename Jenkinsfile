pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker-compose up -d --build'
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