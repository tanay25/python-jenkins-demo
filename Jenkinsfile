pipeline{
    agent any

    stages {
         stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/tanay25/python-jenkins-demo.git',
                    credentialsId: '772485eb-ea9d-44a5-83ab-d0f3d8a70ad8'
            }
        }
        stage('Setup Python') {
            steps {
                bat '''
                python3 -m venv venv
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