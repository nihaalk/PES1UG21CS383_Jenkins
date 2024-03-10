pipeline {

    agent any

    stages {

        stage('Build') {

            steps {
                sh 'g++ pes1ug21cs383.cpp -o output' // Replace with your actual deployment commands
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy' // Replace with your deployment commands (optional)
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
