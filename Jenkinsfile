pipeline {
    agent {
        node{
            label 'master'
        }
    }
    stages {
        stage('Terraform started'){
            steps {
                sh 'echo "Terraform Pipeline is started ... !"'
            }
        }
        stage('Git Cloning'){
            steps {
                checkout scm
            }
        }
        stage('Getting Credentials'){
            steps {
                sh 'sudo cp /home/azureuser/provider.tf /var/lib/jenkins/workspace/Terraform-Deployment-Pipeline/'
            }
        }
        stage('Terraform init'){
            steps {
                sh 'terraform init /var/lib/jenkins/workspace/Terraform-Deployment-Pipeline/'
            }
        }
        stage('Terraform plan'){
            steps {
                sh 'terraform plan /var/lib/jenkins/workspace/Terraform-Deployment-Pipeline/'
            }
        }
        stage ('Approval Required'){
            steps{
                script {
                    def userInput = input(id: 'confirm', message: 'Are you Sure to Deploy Terraform?',
                    parameters: [ [$class: 'BooleanParameterDefination', defaultValue: false,
                    description: 'Apply Terraform', name: 'confirm']])
                }
            }
        }
    }
}