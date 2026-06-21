pipeline {
    agent {
        docker {
            image 'node:18-alpine'       // any Docker Hub image
            args '-u root'               // optional: run as root inside container
        }
    }

    stages {
        stage('Check Environment') {
            steps {
                sh 'node --version'
                sh 'npm --version'
                sh 'whoami'
            }
        }

        stage('Install & Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
    }
}
