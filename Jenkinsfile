pipeline {
    agent any
    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['staging', 'production'],
            description: 'Target environment'
        )
    }
     stages {
        stage('Build') {
            steps {
                echo 'Building ${params.ENVIRONMENT}'
            }
        }
        stage('Tests') {
            parallel {
                stage('Unit') {
                    steps {
                       sh 'echo Running unit tests'
                    }
                 }
                 stage('Integration') {
                    steps {
                        sh 'echo Running intergration tests'
                    }
                }
            }
        }
        stage('Approve') {
            when {
                expression { params.ENVIRONMENT == 'Approve' }
            }
            steps {
                input message: 'Deploy to production?'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying to ${params.ENVIRONMENT}"
            }
        }
    }
    post {
        success {
            echo 'successful!'
        }
        failure {
            echo 'failed!'
        }
    }
}



