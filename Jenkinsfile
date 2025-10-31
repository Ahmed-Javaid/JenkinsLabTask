pipeline { 
    agent any 

    stages { 
        stage('Checkout Code') { 
            steps {
                // Task 3: Print Build Number, Timestamp, and Webhook Message
                echo "Build #${BUILD_NUMBER} triggered by GitHub Webhook at ${new Date()}"
                
                git branch: 'main', url: 'https://github.com/noorulain-nn/task.git'
            }
        }

        stage('Install Dependencies') { 
            steps {
                bat 'npm install'
            }
        } 

        stage('Run Tests') {
            steps {
                bat 'npm test'
            }
        }
    }

    post { 
        success {
            echo 'Build and tests successful!'
        }
        failure {
            echo 'Build failed or tests failed!'
        }
    }
}
