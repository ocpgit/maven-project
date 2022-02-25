pipeline {
    agent any
    tools{
        maven 'wsl-maven'
    }
    stages{
        stage ('build'){
            steps{
                sh 'mvn clean package'
            }
        }   

    }
}
