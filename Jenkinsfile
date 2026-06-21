pipeline {
    agent any

    environment {
        API_TOKEN = credentials('my-api-token')   // binds the secret to an env var
    }

    stages {
        stage('Use Secret') {
            steps {
                // Jenkins automatically masks the value in logs
                sh 'echo "Token length: ${#API_TOKEN}"'
                echo "Token is set: ${API_TOKEN != null}"
            }
        }
    }
}
