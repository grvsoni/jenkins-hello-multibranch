pipeline {
    agent any

    // Define parameters here
    parameters {
        string(name: 'DEPLOY_ENV', defaultValue: 'dev', description: 'Target environment')
        choice(name: 'LOG_LEVEL', choices: ['INFO', 'DEBUG', 'WARN', 'ERROR'], description: 'Level of verbosity')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Check this to run unit tests')
    }

    stages {
        stage('Initialize') {
            steps {
                // Access parameters using params.NAME
                echo "Deploying to: ${params.DEPLOY_ENV}"
                echo "Log level is: ${params.LOG_LEVEL}"
            }
        }
        stage('Test') {
            when {
                expression { return params.RUN_TESTS }
            }
            steps {
                echo 'Running tests...'
            }
        }
    }
}
