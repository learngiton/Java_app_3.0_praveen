@Library("my-aj-own")_

pipeline{
    agent any
    stages{
        stage("echo"){
            steps{
                echo "working"
            }
        }
        stage("checkout"){
           git branch: 'main', url: 'https://github.com/learngiton/Java_app_3.0_praveen.git'
        }
    }
}
