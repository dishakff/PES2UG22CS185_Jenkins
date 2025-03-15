pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/dishakff/PES2UG22CS185_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                sh 'g++ main.cpp -o PES2UG22CS185-1'
                echo 'Build Stage Successful'
            }
        }

        stage('Test') {
            steps {
                sh './PES2UG22CS185-1'
                echo 'Test Stage Successful'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
