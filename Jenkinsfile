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
    }
}