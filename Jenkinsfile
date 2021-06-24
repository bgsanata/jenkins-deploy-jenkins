def appCode = "JEN"
def roleCode = "JENK"

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
            when { not { branch 'master' } }
            steps{
                script{
                    echo "###################### AWS EFS infra with Terraform"
                    deployingEnv = "Dev"
  
                }
            }
        }
        stage("Deploy Jenkins"){
            steps{
                echo "###################### Deploying"
            }
        }
        stage("JCasC"){
            steps{
                echo "###################### setup Jenkins"
            }
        }
        stage("Test"){  
            steps{
                echo "###################### Testing"
            }
        }
    }
}
