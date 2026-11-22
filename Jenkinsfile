pipeline {
    agent any

    stages {
        stage('test') {
            steps {
                echo "testing is done"
            }
        }

        stage('build') {
            steps {
                echo "building is done"
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t family-tracker .'
            }
        }
    }
}
