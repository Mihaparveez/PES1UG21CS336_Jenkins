pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Compile .cpp file using a shell script
                    sh 'g++ -o myExecutable hello.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Print output of .cpp file using a shell script
                    sh './myExecutable'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deployment steps go here (if any)
                    echo 'Deployment completed successfully'
                }
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
            // Additional actions or notifications can be added here
        }
    }

    post {
        success {
            echo 'Pipeline succeeded'
            // Additional actions or notifications for success can be added here
        }
    }
}
