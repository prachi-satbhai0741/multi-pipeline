pipeline {
 agent any
 paramters {
  choice(
   name: 'Environment',
   choices: ['staging', 'production'],
   description:'Environment'
   )
 }
 stages {
  stage('Build') {
   steps {
    echo 'Build'
   }
  }
  stages {
  stage('Test') {
   steps {
    echo 'Test'
   }
  }
  stages {
  stage('Test') {
   steps {
    echo "Deploying to ${params.ENVIRONMENT}
   }
  }
 }
 post {
  success {
   echo "Success"
  }
  failure {
   echo "Fail" 
  }
 }
}

