pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/RamCse05/ansible-jenkins-cicd.git'

            }
        }

        stage('Ping Servers') {
            steps {
                sh 'ansible -i inventory all -m ping'
            }
        }

        stage('Deploy NGINX & Apache') {
            steps {
                sh 'ansible-playbook -i inventory site.yml'
            }
        }
    }
}
