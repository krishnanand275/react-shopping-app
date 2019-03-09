#!/bin/groovy
pipeline {
  tools {
    nodejs 'default-nodejs'
  }
  stages {
    stage('Startup') {
      steps {
        script {
          sh 'npm install'
        }
      }
    }
    stage('Test') {
      steps {
        script {
          sh 'npm run test'
        }
      }
   post {
        always {
          step([$class: 'CoberturaPublisher', coberturaReportFile: 'output/coverage/jest/cobertura-coverage.xml'])
        }
      }
    }
<<<<<<< HEAD
    stage('Build') {
      steps {
        script {
          sh 'npm start'
          sh 'npm pack'
        }
=======
    stage('Deploy'){
      if(env.BRANCH_NAME == 'master'){
        sh 'sudo docker build -t react-app --no-cache .'
        sh 'sudo docker tag react-app localhost:5000/react-app'
>>>>>>> 3a64ae6b13363f79e834586ca4b8644bec31cc84
      }
    }
}
}
