pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    build 'PES1UG22CS255-1'
                    sh 'g++ main.cpp -o output'
                    sh 'g++ -o invalid_output main_invalid.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './output'
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
