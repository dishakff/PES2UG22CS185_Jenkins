pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ main1.cpp -o PES2UG22CS185-1'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './PES2UG22CS185-1'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
