pipeline {
    agent any
    tools {
        maven "M3"
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                script {
                    sh 'mvn test'
                    // Simulate integration tests (replace with actual command if needed)
                    sleep 2
                }
                // Introduce a 2-second delay
                sleep 2
            }
        }

        stage('Code Analysis') {
            steps {
                script {
                    // Simulate code analysis (replace with actual code analysis tool if needed)
                    sleep 2
                }
                // Introduce a 2-second delay
                sleep 2
            }
        }

        stage('Security Scan') {
            steps {
                script {
                    // Simulate security scan (replace with actual security scanning tool if needed)
                    sleep 2
                }
                // Introduce a 2-second delay
                sleep 2
            }
        }

        stage('Deploy to Staging') {
            steps {
                script {
                    // Simulate deployment to staging (replace with actual deployment commands if needed)
                    sleep 2
                }
                // Introduce a 2-second delay
                sleep 2
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                script {
                    sh 'python main.py'  // Assuming 'main.py' is your main application file
                }
                // Introduce a 2-second delay
                sleep 2
            }
        }

        stage('Deploy to Production') {
            steps {
                script {
                    // Simulate deployment to production (replace with actual deployment commands if needed)
                    sleep 2
                }
                // Introduce a 2-second delay
                sleep 2
            }
        }
    }

    post {
        success {
            emailext subject: "Pipeline Successful",
                body: "Your Jenkins pipeline has completed successfully.",
                to: "rumeshranaweera99@gmail.com"
        }
        failure {
            emailext subject: "Pipeline Failed",
                body: "Your Jenkins pipeline has failed. Please check the logs for details.",
                to: "rumeshranaweera99@gmail.com"
        }
    }
}
