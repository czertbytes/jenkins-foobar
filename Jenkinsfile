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
                echo 'deploy staging ...' 
            }
        }
        stage('Deploy Staging') {
            when {
                expression {
                    GIT_BRANCH = sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim().tokenize('/')
                    return !(GIT_BRANCH == 'release')
                }
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
                expression {
                    GIT_BRANCH = sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim().tokenize('/')
                    return !(GIT_BRANCH == 'release')
                }
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