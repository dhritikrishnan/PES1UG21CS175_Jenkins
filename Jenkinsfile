pipeline {
  agent any
  stages {
          stage('Clone repository') {
              steps {
                  checkout([$class: 'GitSCM',
                  branches: [[name: '*/main']],
                  userRemoteConfigs: [['https://github.com/dhritikrishnan/PES1UG21CS175_Jenkins.git']]])
                }
          }
    stage('Build') {
      steps {
        build 'PES1UG21C5175-1.0'
        sh 'get main.cpp -o output'
      }
    }
    stage('Test') {
      steps {
        sh './output'
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy'
      }
    }
    post {
      failure {
        error 'Pipeline failed'
      }
    }
  }
}
