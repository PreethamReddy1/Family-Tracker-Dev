
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test') {
            steps {
                echo "Testing is done"
            }
        }

        stage('Build') {
            steps {
                echo "Building is done"
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t family-tracker .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    docker rm -f travel-app || true
                    docker run -d \
                        --name travel-app \
                        --network travel-network \
                        -p 3001:3000 \
                        family-tracker
                '''
            }
        }
    }
}
