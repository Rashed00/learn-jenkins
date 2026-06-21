pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                python3 -m venv .venv
                . .venv/bin/activate
                pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'pytest'
            }
        }

        stage('Build Artifact') {
            steps {
                sh '''
                mkdir -p dist
                zip -r dist/app.zip .
                '''
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'dist/*.zip'
        }
    }
}
