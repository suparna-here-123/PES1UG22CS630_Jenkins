pipeline {
    agent any  // Runs on any available agent

    stages {
        stage('Clone Repository') {
            steps (
                checkout([$class: 'GitSCM',
                branches: [[name: '*/main]],
                userRemoteConfigs: [[url: 'https://github.com/suparna-here-123/PES1UG22CS630_Jenkins.git']]
                )
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS630-1'
                sh 'g++ main/hello.cpp -o output'
            
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution complete'
        }
        success {
            echo 'Pipeline executed successfully'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}
