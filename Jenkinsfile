pipeline {
    agent any

    stages {

        stage('Clone Source') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Atharvingale/Jenkis_Grafana.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t myapp .'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing successful'
            }
        }

        stage('Deploy') {
            steps {
                bat '''
                docker stop myapp || exit 0
                docker rm myapp || exit 0
                docker run -d -p 3000:3000 --name myapp myapp
                '''
            }
        }
    }
}