pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Naman-cell/jenkins-tester.git'
            }
        }

        stage('code check') {
            steps {
                sh 'pip install flake8'
                sh 'flake8 .'
            }
        }
    }
}
