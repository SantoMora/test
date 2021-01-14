pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo 'Starting Postman Test'
                sh 'newman run Test_1.postman_collection.json -e Test_1.postman_environment.json -d Data.json -n 3'
            }
        }
    }
}