pipeline {
  agent any

  tools {
    maven 'M2_HOME'
    
    }
    stages {
    stage('CheckOut') {
      steps {
        echo 'Checkout the source code from GitHub'
        git 'https://github.com/Pavansai283/bankapp.git' 
            }
    }
    stage ('Configure Test-server with Terraform'){
           steps {
               dir('bankapp'){
                sh 'sudo chmod 600 myEC2key.pem'
                sh 'terraform init'
                sh 'terraform validate'
               sh 'terraform apply --auto-approve'
                }
            }
        }
      }
     }
