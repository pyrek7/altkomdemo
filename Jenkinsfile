pipeline {
    agent any

    stages {
         stage('EnvPreconfig') {
            steps {
                echo 'env selection goes here..'
            }
        } stage('ScriptPolygon') {
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