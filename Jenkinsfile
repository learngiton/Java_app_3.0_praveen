@Library("my-aj-own")_

pipeline {
    agent any

    stages {
        stage("Echo") {
            steps {
                echo "Working"
            }
        }

        stage("Checkout") {
            steps {
                // Cloning the repository from the specified branch
                git branch: 'main', url: 'https://github.com/learngiton/Java_app_3.0_praveen.git'
            }
        }

        stage("Build") {
            steps {
                script {
                    // Call your custom shared library function "maven"
                    maven()
                }
            }
        }

        stage("Condition Check") {
            when {
                branch 'main' // Executes this stage only if the branch is 'main'
            }
            steps {
                echo "Hi Ajay, this is the main branch!"
            }
        }
    }
}
