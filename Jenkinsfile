pipeline{
    agent any
    tools {
        terraform 'jenkins-terraform'
        }
    stages {
        stage('checkout from GIT') {
            steps {
                git branch: 'main', credentialsId: '2ec5da10-6c6f-4f7b-b86b-ae6096f13ad3', url: 'https://github.com/vikasvsnl/Second_terraform_iac_AWS' 
            }
        }
        stage('terraform init') {
            steps {
                bat 'terraform init'
            }
        }
        stage('terraform fmt') {
            steps {
                bat 'terraform fmt'
            }
         }   
        stage('terraform vaidate') {
            steps {
                bat 'terraform validate'
            }
         }
         stage('terraform plan ') {
            steps {
                bat 'terraform plan -var=aws_access_key="AKIA" -var=aws_secret_key="54EUMh"'
            }
        }
    }
}
