Jenkinsfile (Declarative Pipeline)
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy - dev') {
            steps {
                echo 'Deploying....'
                echo 'run unit tests'
            }
        }
        stage('Deploy - Staging') {
            steps {
                /*
                sh './deploy staging'
                sh './run-smoke-tests'
                */
                echo 'deploy staging'
                echo 'run smoke tests'
                }
        }
        stage('Deploy - Production') {
            steps {
                //sh './deploy production'
                echo 'deploy production'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
