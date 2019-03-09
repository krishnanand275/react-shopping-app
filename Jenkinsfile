node {
  try {
    stage('Checkout') {
      checkout scm
    }
    stage('Environment') {
      sh 'git --version'
      echo "Branch: ${env.BRANCH_NAME}"
      sh 'printenv'
    }
    stage('npm instal'){
      sh 'npm install'
    }
    stage('run test'){
     sh 'npm run test -- --coverage'
    }
<<<<<<< HEAD
    stage('Docker_Build'){
      sh 'docker build -t react-app --no-cache .'
=======
    stage('Build'){
      sh 'npm run build'
>>>>>>> ff7ea9060bab38c7922a1fe617f861b1fa779d74
    }
  }
  catch (err) {
    throw err
  }
}
