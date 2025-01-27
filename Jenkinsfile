@Library("my-aj-own")_

parameters{
    
    string(name: 'AJAY', defaultValue:'HI AJAY is displayed', description:'this is default description')
    choice(name: 'CHOICE', defaultValue: ['yes','no'], description:'description')
}

pipeline{
    agent any
    stages{
        stage("echo"){
            steps{
                echo "working"
            }
        }
        stage("checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/learngiton/Java_app_3.0_praveen.git'
            }
        }
        stage("build"){
           steps{
               script{
                   maven()
               }
           } 
        }
        stage("condition check"){
            when{
                expression{params.CHOICE == 'yes'}
            }
            steps{
                echo "hi ajay "
            }
        }
        stage("check for input"){
            steps{
                input message: 'Hi are you Ajay'?, OK: 'yes'
            }
        }
    }
}
