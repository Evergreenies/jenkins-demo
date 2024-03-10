pipeline {
    agent any
    
    environment {
        name = 'Suyoog Shimpi'
    }
    
    parameters {
        string(name: 'person', defaultValue: 'Suyog Shimpi', description: 'testing parementeres')
        booleanParam(name: 'isMale', defaultValue: true, description: '')
    }

    stages {
        stage('test') {
            steps {
                echo 'testing'
                sh 'date'
                sh 'pwd'
                sh '''
                whoami
                date
                ls 
                pwd
                '''
            }
        }
        stage('build') {
            steps {
                echo 'building artifacts'
                sh 'echo "${BUILD_ID} ${name}"'
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo 'deploy tp dev'
                sh 'echo "${person} ${isMale}"'
            }
        }
        stage('deploy-to-test') {
            steps {
                echo 'deploy to test'
            }
        }
        stage('deploy-to-stage') {
            steps {
                echo 'deploy to stage'
            }
        }
        stage('deploy-to-prod') {
            input {
                message "Should we continue?"
                ok "Yes! Go Ahead.."
            }
            
            steps {
                echo 'deploy to prod'
            }
        }
    }
    post {
        always {
            echo 'I am always there...'
        }   
    }
}

