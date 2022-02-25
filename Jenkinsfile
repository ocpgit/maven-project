pipeline {
    agent any
    tools{
        maven 'wsl-maven'
    }
    stages{
        stage ('build'){
            steps{
                sh 'mvn clean package'
                sh "docker -H localhost:2375 build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }   

    }
}
