pipeline {
    agent any
    tools{
        maven 'wsl-maven'
    }
    stages{
        stage ('build'){
            steps{
                sh 'mvn clean package'
                sh "docker build -H 192.168.2.100 . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }   

    }
}
