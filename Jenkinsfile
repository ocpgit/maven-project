pipeline {
    agent any
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
}
