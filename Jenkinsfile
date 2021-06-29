pipeline {
    options {
      disableConcurrentBuilds()
      buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
      timeout(time: 300, unit: 'SECONDS')
    }
    
    agent any

    stages {

        stage("Terraformation"){
            agent { label '' }
            when { branch 'main' } 
            steps{
                script{
                    echo "###################### AWS EFS infra with Terraform ######################"
                    deployingEnv = "DEV"
                }
            }
        }

        stage("Helming"){
            steps{
                echo "###################### Deploying ######################"
//                 withCredentials([usernamePassword(credentialsId: 'jenkins_bind_password', usernameVariable: 'USERNAME', passwordVariable: 'BIND_PASSWORD')]) {
//                 withAWS (credentials: "123") {
//                 }}
            }
        }

        stage("JCasC"){
            steps{
                echo "###################### setup Jenkins ######################"
            }
        }

        stage("Test"){  
            steps{
                echo "###################### Testing ######################"
            }
        }
    }

    post {
        always {
            cleanWs()
            }
        }

}
