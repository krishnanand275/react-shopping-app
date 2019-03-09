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
    stage('Build'){
      sh 'npm build'
    }
  }
  catch (err) {
    throw err
  }
}
