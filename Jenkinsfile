pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello from Jenkins!'
                sh 'echo "Running on: $(uname -a)"'
                sh 'pwd'
            }
        }

        stage('Check Tools') {
            steps {
                sh 'git --version'
                sh 'java -version'
            }
        }
    }
}
