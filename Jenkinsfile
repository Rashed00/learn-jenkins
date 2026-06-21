pipeline {
    agent any

    environment {
        APP_NAME = 'learn-jenkins'
        BUILD_AUTHOR = 'Rashed'
    }

    parameters {
        string(name: 'ENVIRONMENT', defaultValue: 'staging', description: 'Target environment')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Should tests run?')
    }

    stages {
        stage('Print Info') {
            steps {
                echo "App: ${APP_NAME}"
                echo "Build #: ${BUILD_NUMBER}"          // built-in Jenkins var
                echo "Branch: ${GIT_BRANCH}"             // built-in Jenkins var
                echo "Deploying to: ${params.ENVIRONMENT}"
                echo "Workspace: ${WORKSPACE}"
            }
        }

        stage('Conditional Test') {
            when {
                expression { params.RUN_TESTS == true }
            }
            steps {
                echo 'Running tests...'
                sh 'echo "Tests passed!"'
            }
        }
    }
}
