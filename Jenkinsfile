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
        stage('Deploy Develop') {
            steps {
                echo 'deploy develop ...' 
            }
        }
        stage('Deploy Staging') {
            when {
                beforeInput true
                tag "release-*"
            }
            input {
                message "Should we deploy to Staging?"
                ok "Yes, we should."
            }
            steps {
                echo 'deploy staging ...' 
            }
        }
        stage('Deploy Production') {
            when {
                beforeInput true
                tag "release-*"
            }
            input {
                message "Should we deploy to Production?"
                ok "Yes, we should."
            }
            steps {
                echo 'deploy prod ...' 
            }
        }
    }
}