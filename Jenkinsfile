pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            steps {
                cleanWs()
                git branch: 'master', url: 'https://github.com/Nifleheim/ansible'
            }
        }
        
        stage('Update Kube-Config') {
            steps {
                sh 'aws eks update-kubeconfig --region ap-southeast-2 --name cilsy-final'
            }
        }
        
        stage('Ansible Execute') {
            steps {
                ansiblePlaybook disableHostKeyChecking: true, installation: 'ansible1', playbook: 'main.yml'
            }
        }
    }
}

