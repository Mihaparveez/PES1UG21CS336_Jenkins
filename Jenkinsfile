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
                    // Intentional error in deployment steps
                    sh 'echo "Simulating deployment error" && exit 1'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded'
            // Additional actions or notifications for success can be added here
        }

        failure {
            echo 'Pipeline failed'
            // Additional actions or notifications can be added here
        }
    }
}
