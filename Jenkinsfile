pipeline {
  agent any
  stages {
    stage('Stop all') {
      steps {
        sh 'docker-compose down'
      }
    }
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
      }
    }
  }
}
