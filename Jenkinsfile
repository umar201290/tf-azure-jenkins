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
    }
}