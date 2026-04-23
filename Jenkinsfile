pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t myapp .'
            }
        }

        stage('Deploy Container') {
            steps {
                bat '''
                docker stop myapp
                docker rm myapp
                docker run -d -p 80:80 --name myapp myapp
                '''
            }
        }
    }
}
