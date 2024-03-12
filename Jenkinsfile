pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub
                git 'https://github.com/Naman-cell/jenkins-tester.git'
            }
        }
        
        stage('PEP8 Check') {
            steps {
                // Install flake8
                sh 'pip install flake8'
                
                // Run PEP8 check
                script {
                    def pep8Output = sh(script: 'flake8 .', returnStdout: true).trim()
                    if (pep8Output.isEmpty()) {
                        echo 'PEP8 conventions followed.'
                    } else {
                        echo 'PEP8 is not followed:'
                        echo pep8Output
                    }
                }
            }
        }
    }
}
