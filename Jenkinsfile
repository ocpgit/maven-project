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
        stage ('Deploy to staging'){
            steps{
                build job:'deploy-to-staging'
            }
        }
        stage ('Deploy to Production'){
            steps{
                timeout(time:5, unit:'DAYS'){
                    input message:'Deploy to production env?' 
                }

                build job: 'deploy-to-production'
            }
            post {
                success {
                    echo ' ! Success to deploy new version to production env ! '
                }

                failure {
                    echo ' !!! Failed to deploy new version to production env !!! '
                }
            }
        }

    }
}
