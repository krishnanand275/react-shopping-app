node {
  try {
    stage('Checkout') {
      checkout scm
    }
    stage('Environment') {
      sh 'git --version'
      echo "Branch: ${env.BRANCH_NAME}"
      sh 'docker -v'
      sh 'printenv'
    }
    stage('Build Docker test'){
      sh 'sudo docker build -t react-test -f Dockerfile.test --no-cache . '
    }
    stage('Docker test'){
      sh 'sudo docker run --rm react-test'
    }
    stage('Clean Docker test'){
      sh 'sudo docker rmi react-test'
    }
    stage('Deploy'){
      if(env.BRANCH_NAME == 'master'){
        sh 'sudo docker build -t react-app --no-cache .'
        sh 'sudo docker tag react-app localhost:5000/react-app'
      }
    }
  }
  catch (err) {
    throw err
  }
}
