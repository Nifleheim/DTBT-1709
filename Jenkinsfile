pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            steps {
                cleanWs()
                git branch: 'master', url: 'https://github.com/Nifleheim/DTBT-1709'
            }
        }
        
        dir('ansible') {
            ansiblePlaybook disableHostKeyChecking: true, installation: 'ansible1', playbook: 'main.yml'
        }
        

    }
}

