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
      sh  'npm audit --fix
    }
    stage('run test'){
     sh 'npm run test -- --coverage'
    }
    stage('Docker_Build'){
      sh 'docker build -t react-app --no-cache .'
    }
   }
  catch (err) {
    throw err
  }
}
