pipeline {
    agent {
        docker { image 'alpine:latest' }
    }

    stages {
        stage('Clone') {
            steps {
                echo 'Hello world!' 
            }
        }
        stage('Compile') {
            steps {
                echo 'compile ...' 
            }
        }
        stage('Package') {
            steps {
                echo 'package ...' 
            }
        }
        stage('Deploy Staging') {
            input "Deploy to Staging?"
        }
        stage('Deploy to Staging')
            steps {
                echo 'deploy staging ...' 
            }
        }
        stage('Deploy Prod') {
            input "Deploy to Production?"
        }
        stage('Deploy to Production')
            steps {
                echo 'deploy prod ...' 
            }
        }
    }
}