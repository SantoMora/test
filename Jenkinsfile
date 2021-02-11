pipeline {
    agent any
    parameters {
        string(name: 'NAME', defaultValue: 'Mauricio', description: 'Name of User')
        booleanParam(name: 'TEST', defaultValue: true, description: 'Run Test stage?')
        choice(name: 'STAGE', choices: ['All', 'Puppet', 'Gradle', 'Ansible'], description: 'Select an specific stage or run all')
    }
    stages {
        stage('SCM') {
            steps {
                echo 'Cloning'
            }
        }
        stage('Start') {
            steps {
                echo "Hello ${params.NAME}"
            }
        }
        stage('Test') {
            when {
                expression { return params.TEST}
            }
            steps {
                echo 'Running test....'
            }
        }
        stage('Puppet') {
            when {
                expression { return params.STAGE == 'All' || params.STAGE == 'Puppet'}
            }
            steps {
                echo 'Puppet'
            }
        }
        stage('Gradle') {
            when {
                expression { return params.STAGE == 'All' || params.STAGE == 'Gradle'}
            }
            steps {
                echo 'Gradle'
            }
        }
        stage('Ansible') {
            when {
                expression { return params.STAGE == 'All' || params.STAGE == 'Ansible'}
            }
            steps {
                echo 'Ansible'
            }
        }
    }
}