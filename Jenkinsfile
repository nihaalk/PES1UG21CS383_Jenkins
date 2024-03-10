pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    try {
                        // Compile the new.cpp file
                        sh 'g++ new.cpp -o output'
                        
                        // Trigger the 'pes1ug21cs383-1' Jenkins job (assumed it exists)
                        build job: 'pes1ug21cs383-1'
                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        error "Build failed: ${e.message}"
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    try {
                        // Print output of the compiled C++ program
                        sh './output'
                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        error "Test failed: ${e.message}"
                    }
                }
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
            echo 'Pipeline failed'
        }
    }
}

