pipeline {
    agent any

    environment {
        DIRECTORY_PATH = "./src"
        TESTING_ENVIRONMENT = "./environments/staging"
        PRODUCTION_ENVIRONMENT = "./environments/production"
    }

    stages {
        stage('Load Environment Variables') {
            steps {
                echo "Environment variables loaded."
            }
        }

        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artefacts"
            }
        }

        stage('Test') {
            steps {
                echo "Unit tests"
                echo "Integration tests"
            }
        }

        stage('Code') {
            steps {
                echo "Check the quality of the code"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for manual approval (simulated)..."
                sleep time: 10, unit: 'SECONDS'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying code to production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
