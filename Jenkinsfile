pipeline {
    agent any
    environment {
        MainEnvConfig = 'developenvconfig'
    }
    stages {
         stage('Env') {
            when {
                branch 'develop'
            }
            steps {
                echo "we need to do ${MainEnvConfig} in order to make it work"
            }
        } 
        stage('Scripts') {
            steps {
                echo 'scripts goes here..'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Clean') {
            steps {
                echo 'Cleaning....'
            }
        }
    }
}
