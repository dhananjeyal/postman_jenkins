pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh "cd ${env.WORKSPACE}"
                sh label: 'API Collection Tests', script: 'newman run tests/API_Tests.postman_collection.json -e environment/API_Environment.postman_environment.json -d tests/data.json --suppress-exit-code'
            }
        }
    }
}