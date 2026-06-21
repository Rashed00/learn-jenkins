pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mkdir -p build && echo "artifact" > build/output.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                // Uncomment to simulate failure:
                sh 'exit 1'
            }
        }
    }

    post {
        always {
            echo "Build finished. Status: ${currentBuild.currentResult}"
            echo 'Cleaning workspace...'
            cleanWs()   // deletes workspace files
        }
        success {
            echo 'SUCCESS — would send green notification here'
        }
        failure {
            echo 'FAILURE — would alert the team here'
        }
        unstable {
            echo 'UNSTABLE — tests had issues'
        }
    }
}
