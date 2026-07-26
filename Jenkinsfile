pipeline {
    agent any
    parameters {
        choice ('Name': 'EN'),choices ('staging', 'production'),description ('Test environment')
    }
    ENVIRONMENT {
        APP_NAME = TEST
    }
    stages {
        parallel {
        stage(Build) {
            steps{
                sh 'echo Building for ${params.ENV}'
            }
        }
     stages(Test) {
           stage(Unit)
            {
             steps{
                sh 'echo testing unit'
             }
        }
         stage(Integration) {
            steps{
                sh 'echo Integration'
            }
        }
         stage(Deploy) {
            steps{
                sh 'echo deploy'
            }
        }
     }
    post {
        success {
            echo "deploy sucess"
        }
        failure {
            echo "deploy fail"
        }
    }
 }
        



