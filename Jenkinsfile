pipeline {
    agent any
    
    stages {
        stage('cloning') {
            steps {
                // Checkout code from GitHub
                git clone 'https://github.com/Naman-cell/jenkins-tester.git'
                cd jenkins-tester
                echo "entering the first stage"
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
