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
            post {
                success {
                    echo 'starting archiving artifacts...'
                    archiveArtifacts artifacts: '**/target/*.war'
        
                }
           }
        }
}
