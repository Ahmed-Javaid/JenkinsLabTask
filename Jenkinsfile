// Sample Jenkinsfile content based on the task requirement
pipeline { // Defines the entire workflow 
    agent any // Tells Jenkins to execute the pipeline on any available agent [cite: 14]

    stages { // Contains the sequence of stages

        stage('Checkout Code') { // First stage to clone the code 
            steps {
                // Configure it to pull code from the GitHub repository using the Git plugin [cite: 6]
                git branch: 'main', url: 'https://github.com/noorulain-nn/task.git'
            }
        }

        stage('Install Dependencies') { // Stage to install Node.js packages
            steps {
                bat 'npm install' // Runs the npm install command
        }

        stage('Run Tests') { // Stage to execute the project's tests
            steps {
                bat 'npm test' // Runs the npm test command
            }
        }
    }

    post { // Actions that run after all stages are complete
        success {
            echo 'Build and tests successful!' // Display success status
        }
        failure {
            echo 'Build failed or tests failed!' // Display failure status 
        }
    }
}
