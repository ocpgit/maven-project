pipeline {
    agent any
    tools{
        maven 'wsl-maven'
    }
    stages{
        stage ('build'){
            steps{
                sh 'mvn clean package'
                sh "docker -H 192.168.2.100 build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }   

    }
}
