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
        sh 'docker ps -a'
        sh 'docker images -a'
        sh 'docker volume ls'
        sh 'docker network ls'
      }
    }
    stage('Turndown') {
      steps {
        input 'Terminaste con las pruebas?'
        sh 'docker-compose down'
      }
    }
  }
}
