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
            steps {
              parallel (
                    "TaskOne" : {
                        echo 'task one stuff part 1'
                        echo 'task one stuff part 2'
                        echo 'task one stuff part 3'
                    },
                    "TaskTwo" : {
                        echo 'tasl two stuff part 1'
                        echo 'tasl two stuff part 2'
                    }
                    )
            }
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