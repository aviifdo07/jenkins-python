pipeline {
    agent any
    tools {
        maven "M3"
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Build the code using a build automation tool (e.g., Maven)
                    // Replace 'mvn clean package' with the appropriate build command for your code
                    sh 'mvn clean package'
                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                script {
                    // Run unit tests using a test automation tool (e.g., JUnit)
                    sh 'mvn test'

                    // Run integration tests (if applicable) using a suitable tool
                    // Replace 'python integration_tests.py' with the command for your integration tests
                    sh 'py integration_tests.py'
                }
            }
        }

        stage('Code Analysis') {
            steps {
                script {
                    // Integrate a code analysis tool (e.g., SonarQube) to analyze the code
                    // Replace 'mvn sonar:sonar' with the appropriate command for code analysis
                    withSonarQubeEnv('SonarQubeServer') {
                        sh 'mvn sonar:sonar'
                    }
                }
            }
        }

        stage('Security Scan') {
            steps {
                script {
                    // Perform a security scan using a security scanning tool (e.g., OWASP ZAP)
                    // Replace 'zap-cli --url http://yourappurl.com --quick-scan' with the appropriate command
                    sh 'zap-cli --url http://yourappurl.com --quick-scan'
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                script {
                    // Deploy the application to a staging server (e.g., AWS EC2 instance)
                    // Replace these commands with the actual deployment commands for your staging environment
                    sh 'aws s3 cp yourapp.jar s3://your-bucket-name'
                    sh 'aws ec2 run-instances ...'
                }
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                script {
                    // Run integration tests on the staging environment
                    // Replace 'python integration_tests_staging.py' with the appropriate command for your staging tests
                    sh 'python integration_tests_staging.py'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                script {
                    // Deploy the application to a production server (e.g., AWS EC2 instance)
                    // Replace these commands with the actual deployment commands for your production environment
                    sh 'aws s3 cp yourapp.jar s3://your-bucket-name'
                    sh 'aws ec2 run-instances ...'
                }
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
