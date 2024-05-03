pipeline {
    agent any
    environment {
        name = 'gur'
    } 
    parameters {
        string(name: 'person', defaultValue: 'gurdev', description: "who are you?")
    }
    stages {
        stage('environment variable') {
            steps {
                sh 'echo "${name}"'
                sh 'echo "${BUILD_ID}"' 
            }
        } 
        stage('build') {
            steps {
                sh '''
                ls
                pwd
                date
                '''
                echo 'build'
            }
        }
        stage('parameter') {
            steps {
                echo 'deploy om test'
                sh 'echo "${person}"'
            }
        }
        stage('continue') {
            input {
                message "Should we continue?"
                ok "yes we should"
            }
            steps {
                echo "deploy on test"
            }
        }
        stage('deploy on prod') {
            steps {
                echo 'deploy on prod'
            }
        }
    }
    post {
        always {
            echo 'i will always say hello again!'
        }
    }
}
