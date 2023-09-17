pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            steps {
                cleanWs()
                git branch: 'dev', url: 'https://github.com/Nifleheim/DTBT-1709'
            }
        }
        
        dir('Ansible') {
            ansiblePlaybook disableHostKeyChecking: true, installation: 'ansible1', playbook: 'main.yml'
        }
        

    }
}
