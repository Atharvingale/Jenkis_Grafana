pipeline {
    agent any

    stages {

        stage('Clone Source') {
            steps {
                git 'https://github.com/yourusername/repo.git'
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
