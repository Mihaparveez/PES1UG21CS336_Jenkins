pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Assuming 'PES1UG21CS336-1' is the name of your Jenkins job
                    build job: 'PES1UG21CS336-1', wait: false

                    // Compile main.cpp using g++
                    sh 'g++ main.cpp -o output'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run the compiled output
                    sh './output'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploy'
                    // Add deployment steps if needed
                }
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
