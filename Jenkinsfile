@Library("my-aj-own")_

pipeline {
    agent any

    parameters {
        string(name: 'AJAY', defaultValue: 'HI AJAY is displayed', description: 'this is default description')
        choice(name: 'CHOICE', choices: ['yes', 'no'], description: 'description') // Fixed choice parameter definition
    }

    stages {
        stage("echo") {
            steps {
                echo "working"
            }
        }
        stage("checkout") {
            steps {
                git branch: 'main', url: 'https://github.com/learngiton/Java_app_3.0_praveen.git'
            }
        }
        stage("build") {
            steps {
                script {
                    maven()
                }
            }
        }
        stage("condition check") {
            when {
                expression { params.CHOICE == 'yes' } // Checks if the 'CHOICE' parameter is set to 'yes'
            }
            steps {
                echo "Hi Ajay, condition met!"
            }
        }
    }
}
