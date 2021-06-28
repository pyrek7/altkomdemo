pipeline {
    agent any
    environment {
        MainEnvConfig = 'someconfiguration'
        dotnet = '"C:\\Program Files\\dotnet\\dotnet.exe"'
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
           def a = 5
           println a
        }
        stage('Build') {
            steps {
                dir("Calculator"){
                    bat "${dotnet} build"
                }
            }
        }
        stage('Test') {
            steps {
                 dir("CalculatorTests"){
                    bat "${dotnet} test"
                }
            }
        }
        stage('Clean') {
            steps {
                 dir("Calculator"){
                    bat "${dotnet} clean"
                }
                  dir("CalculatorTests"){
                    bat "${dotnet} clean"
                }
            }
        }
    }
}