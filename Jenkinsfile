pipeline {
    agent any

    environment {
        ENV_FILE = 'env.properties'
    }

    stages {
        stage('Load Environment Variables') {
            steps {
                script {
                    def props = readProperties file: "${ENV_FILE}"
                    env.DIRECTORY_PATH = props['DIRECTORY_PATH']
                    env.TESTING_ENVIRONMENT = props['TESTING_ENVIRONMENT']
                    env.PRODUCTION_ENVIRONMENT = props['PRODUCTION_ENVIRONMENT']
                }
                echo "Loaded environment variables from ${ENV_FILE}"
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
