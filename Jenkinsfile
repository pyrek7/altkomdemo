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
              parallel (
                    "TaskOne" : {
                       def a = 5
                    },
                    "TaskTwo" : {
                        echo 'tasl two stuff part 1'
                        echo 'tasl two stuff part 2'
                    }
                    )
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