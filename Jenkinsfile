pipeline {
    agent any
    
    // stages {
    //     stage('Build') {
    //         steps {
    //             script {
    //                 // Build your code (not specified in your example, assuming Python)
    //                 sh 'python setup.py build'
    //             }
    //         }
    //     }
        
        stage('Run main.py') {
            steps {
                script {
                    // Run main.py after the build
                    sh 'python main.py'
                }
            }
        }
        
        // Other stages as per your requirements...
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
