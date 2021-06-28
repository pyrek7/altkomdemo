pipeline {
    agent any
    environment {
        MainEnvConfig = 'someconfiguration'
    }
    stages {
         stage('Env') {
            when {
                branch 'main'
            }
            steps {
                echo "we need to do ${MainEnvConfig} in order to make it work"
            }
        } 
        stage('Scripts') {
            steps {
               parallel (
                   "TaskOne"{
                       echo "task one line one"
                       echo "task one line two"
                   }
                   "TaskTwo"{
                        echo "task two line one"
                       echo "task two line two"
                   }
               )
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