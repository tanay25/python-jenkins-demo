pipeline{
    agent any

    stages {
        stage('Checkout'){
            steps {
                git 'https://github.com/tanay25/python-jenkins-demo.git'
            }
        }
        stage('Setup Python') {
            steps {
                bat '''
                python -m venv venv
                call venv/Scripts/activate
                pip install -r requirements.txt
                '''
            }

        }
        stage('Run App'){
            steps{
                bat '''
                    call venv/Scripts/activate
                    pytest
                '''
            }
        }
    }

}